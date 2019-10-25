# AutoConfig

Gunbot AutoConfig is a collection of filter tools you can use to dynamically manage your config files.   
You can create "jobs" to do something you would normally do by hand, for example scan an exchange for potential pairs to add, and schedule the job in a cron-like format.

Things you can currently do with Autoconfig:

* Scan exchanges and automatically add pairs, for example add pairs with volume &gt; 500 BTC and for which price is rising.
* Scan exchanges to remove pairs from your config. For example remove pairs without quote balance for which volume has dropped below 100 BTC.
* Monitor pair state information and automatically set pair overrides. For example set a different DU\_BUYDOWN after the first round of DU happened.



## How it works

There is a single config file for AutoConfig \(autoconfig.json\), which can contain many jobs. As soon as Gunbot starts or the config file is changed, all jobs in the config are scheduled \(any pre-existing scheduled job is removed in this process\).

When a job is processed, changes to config.js are only made for pairs that have passed every filter.

* The config file can have one or many jobs
* One job can have one or many filters
* Within a job, you can set filters for which pairs it applies

If a job successfully completes, the changes are written to config.js and gunbot restarts using the new settings. If a job causes no changes, for example because it tries to place already existing overrides, it won't be written to file.

Schedules are set in a format similar to how cron jobs are set. If you're not used to the format, use a website like [https://crontab-generator.org/](https://crontab-generator.org/) to generate it.

Exchange names must be set like ccxt lists the id's here: [https://github.com/ccxt/ccxt/wiki/Exchange-Markets](https://github.com/ccxt/ccxt/wiki/Exchange-Markets)



## Config examples

### Adding pairs

Below is a config example that would scan Binance and add BTC-x pairs when they meet the filter criteria.

You must have at least one pair set per exchange you use this job type on.

Filter options are described later in this article.

**Pair options:**

  
**exclude**: excluded pairs \(processed last\). Any pair on the exchange that matches any of the excludes, won't be processed. Excluded items do not need to be whole pair names, as long as part of the string matches an actual pair, it will be excluded. Input as comma separated list, does not accept spaces between items. Can be empty.

**include:** included pairs \(processed first\). Any pair on the exchange that matches any of the includes, will be processed \(after also processing excluded\). Included items do not need to be whole pair names, as long as part of the string matches an actual pair, it will be included. Input as comma separated list, does not accept spaces between items. Can not be empty.

**maxPairs:** maximum number of allowed pairs. In case a filter action would result in more pairs than this setting, the config will be filled up to the max number of allowed pairs. 

#### Other options:

**type:** must be set to `addPairs` 

**snapshots:** defines how many ticker snapshots are saved to perform calculations on. Relevant for filtertypes that include `Interval` in their name. For example: snapshots is set to 10, this means that the ticker data for the last 10 times the job runs are saved and some of the values in it are used for calculating average values over time. For now, snapshot data gets cleared when Gunbot restarts.3

**strategy:** this defines the strategy that will be assigned to pairs added by this job.

```text
{
    "addMoon": {
      "pairs": {
        "exclude": "",
        "include": "BTC-",
        "maxPairs": 25,
        "exchange": "binance"
      },
      "filters": {
        "filter1": {
          "type": "minPrice",
          "min": 0.0000001 
        },
        "filter2": {
          "type": "maxPrice",
          "max": 0.0000010 
        },
        "filter3": {
          "type": "minPricePctChangeInterval",
          "min": 0.00002 
        },
        "filter4": {
          "type": "maxPricePctChangeInterval",
          "max": 1 
        },
        "filter5": {
          "type": "minVolumePctChangeInterval",
          "min": 10
        },
        "filter6": {
          "type": "maxVolumePctChangeInterval",
          "max": 50 
        },
        "filter7": {
          "type": "minVolume24h",
          "min": 500 
        },
        "filter8": {
          "type": "maxVolume24h",
          "max": 1000 
        },
        "filter9": {
          "type": "minVolatilityPct24h",
          "min": 1 
        },
        "filter10": {
          "type": "maxVolatilityPct24h",
          "max": 1 
        },
        "filter11": {
          "type": "minSpreadPct",
          "min": 0.00001
        },
        "filter12": {
          "type": "maxSpreadPct",
          "max": 1 
        }
      },
      "schedule": "* * * * *",
      "type": "addPairs",
      "snapshots": 2
    }
  }
```



### Removing pairs

Below is a config example that would scan Binance and remove pairs from your config when they meet the filter criteria. Only the pairs that Gunbot already cycled in it's current session can be filtered.

You must have at least one pair set per exchange you use this job type on.

Filter options are described later in this article.

**Pair options:**

**exclude**: pairs that should not be scanned for possible removal. Any active pair that matches any of the excludes, won't be processed. Excluded items do not need to be whole pair names, as long as part of the string matches an actual pair, it will be excluded. Input as comma separated list, does not accept spaces between items. Can be empty.

**noBag** \(true/false\): when true, only pairs with a balance below mvts are filtered for possible removal. When set to false, all pairs in config are filtered.

#### Other options:

**type:** must be set to `removePairs` 

**snapshots:** defines how many ticker snapshots are saved to perform calculations on. Relevant for filtertypes that include `Interval` in their name. For example: snapshots is set to 10, this means that the ticker data for the last 10 times the job runs are saved and some of the values in it are used for calculating average values over time. For now, snapshot data gets cleared when Gunbot restarts.

```text
{
  "removeCrap": {
    "pairs": {
      "exclude": "BNB,XVG",
      "noBag": false,
      "exchange": "binance"
    },
    "filters": {
      "filter2": {
        "type": "maxPrice",
        "max": 0.00000002
      }
    },
    "schedule": "* * * * *",
    "type": "removePairs",
    "snapshots": 10
  }
}
```



### Managing overrides

Filter options are described later in this article.

**exclude**: excluded pairs \(processed last\). Any active pair that matches any of the excludes, won't be processed. Excluded items do not need to be whole pair names, as long as part of the string matches an actual pair, it will be excluded. Input as comma separated list, does not accept spaces between items. Can be empty.

**include:** included pairs \(processed first\). Any active pair that matches any of the includes, will be processed \(after also processing excluded\). Included items do not need to be whole pair names, as long as part of the string matches an actual pair, it will be included. Input as comma separated list, does not accept spaces between items. Can not be empty.

**overrides**: contain one or more overrides, these will be set for each pair that passes all filters when a job is executed.

**clearOverrides** \(true/false\): when set to true, all existing overrides for a pair are removed before placing the new ones.

**type**: must be set to `manageOverrides`



```text
{
	"DynamicDU1": {
		"pairs": {
			"exclude": "DOGE,ETH",
			"include": "USDT,BNB",
			"exchange": "binance"
		},
		"filters": {
			"ducount": {
				"type": "exact",
				"ducount": 1
			}
		},
		"overrides": {
			"DU_BUYDOWN": 3
		},
		"clearOverrides": false,
		"schedule": "*/10 * * * *"
  },
  "DynamicDU2": {
		"pairs": {
			"exclude": "DOGE,ETH",
			"include": "USDT,BNB",
			"exchange": "binance"
		},
		"filters": {
			"ducount": {
				"type": "exact",
				"ducount": 2
			}
		},
		"overrides": {
      "DU_BUYDOWN": 8,
      "GAIN": 1
		},
		"clearOverrides": false,
		"schedule": "1 * * * *"
  },
  "MMshort": {
		"pairs": {
			"exclude": "",
			"include": "XBT-USD",
			"exchange": "bitmex"
		},
		"filters": {
			"side": {
				"type": "exact",
				"state": "SHORT"
			},
			"liquidationDistance": {
				"type": "differenceSmaller",
				"liquidationPrice": 1,
				"avgEntryPrice": 1,
				"delta": 90
			}
		},
		"overrides": {
			"MAX_SELL": 0
		},
		"clearOverrides": true,
		"type": "manageOverrides",
		"schedule": "* * * * *"
	}
}
```



## Filter options

### Adding & removing pairs

You can use the following filter types for adding and removing pairs. Please note that not every filter type is available for every exchange, due to the fact that some exchanges don't offer the required data.

Filter for price use ask when adding pairs and bid when filtering for removal.

* `minPrice`: filter returns true when price is higher than set.
* `maxPrice`: filter returns true when price is lower than set.
* `minPricePctChangeInterval`: filter returns true if the current price is at least x% higher than the average price of all snapshots. Only executed when max snapshot sample size is reached.
* `maxPricePctChangeInterval`: filter returns true if the current price is at least x% lower than the average price of all snapshots. Only executed when max snapshot sample size is reached.
* `minVolumePctChangeInterval`: filter returns true if the current 24h volume is at least x% higher than the average 24h volume of all snapshots. Only executed when max snapshot sample size is reached.
* `maxVolumePctChangeInterval`: filter returns true if the current 24h volume is at least x% lower than the average 24h volume of all snapshots. Only executed when max snapshot sample size is reached.
* `minVolume24h`: filter returns true if 24h volume is higher than set, volume in base.
* `maxVolume24h`: filter returns true if 24h volume is higher than set, volume in base.
* `minVolatilityPct24h`: filter returns true if 24h price percentage change is higher than set.
* `maxVolatilityPct24h`: filter returns true if 24h price percentage change is lower than set.
* `minSpreadPct`: filter returns true if percentage difference between bid and ask is higher than set.
* `maxSpreadPct`: filter returns true if percentage difference between bid and ask is lower than set.

![Available data at supported exchanges. Other ccxt exchanges might work as well.](../.gitbook/assets/image%20%288%29.png)



### Managing overrides

![](../.gitbook/assets/image%20%2834%29.png)


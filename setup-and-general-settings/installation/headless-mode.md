# Headless mode

{% hint style="info" %}
This article is meant for power users who want to run bitRage without using the GUI.

This is not an exhaustive overview of all available settings, just a quick overview of how to manually work with the config file. Refer to other parts of the wiki for detailed settings descriptions.
{% endhint %}

## Config file system

All bitRage settings are defined in a single file named `config.json`. This is where you set up your exchange API keys, add pairs and define strategy settings.

You can refer to the included `config-json-example.txt` file for an example of a config file with properly defined pairs and all needed parameters for adding each exchange. Throughout this wiki you'll find detailed descriptions for every parameter available in the config file.

When the config file is overwritten while bitRage is running, the changed settings will be loaded automatically.

Make sure that no parameters are removed when setting it up. Make sure the JSON-formatting stays intact. If you are unsure about your config file, you can validate it on [https://jsonlint.com](https://jsonlint.com) \(or a similar JSON validator\).

The only actions that require using the GUI are:

* tbd

## Disabling the GUI

To disable the GUI completely, make the following change in the GUI section of `config.json`:

```text
"GUI": {
        "enabled": false,
```

## Connecting exchanges

To connect an exchange, add the relevant settings to the exchange section of `config.json`. 

Gunbot and bitRage share the same license system, you must use masterkeys that are already registered to be used with Gunbot.

It looks like this:

```text
"binance": {
            "masterkey": "Registered API",
            "mastersecret": "SECRET",
            "key": "API",
            "secret": "SECRET",
            "key2": "API",
            "secret2": "SECRET",
            "delay": 10,
            "REST_delay": 10,
            "TRADING_FEES": 0.25,
            "TRADES_INTERVAL": 10,
            "filteredPairs": ["BTC","USD","USDT"],
            "includeCoins": ["BTC","USD","USDT"],
            "filteredBags": ["BTC","USD","USDT","EUR"],
            "Volume1st": {"XMR":100},
            "Volume2nd": {"XMR":100,"MAID":100},
            "Volume3rd": {"MAID":100}
        }
```

Note that you can use a different API key for trading than the registered key. If you don't use a secondary key, you can just enter the registered key in the `key` parameter.

The `key2` field requires a different API key from `key`, it does not need to be registered on the license server.

## Strategies

A strategy is defined in the `strategies` section of the config file. This strategy can then be assigned to one or more trading pairs. 

For now, there is only one strategy called "bitrage", you can't copy/rename it to run variants.

It looks like this:

```text
"bitrage": {
            "BTC": 0.002,
            "USDT": 20,
            "USDC": 20,
            "USD": 20,
            "EUR": 20,
            "GBP": 20,
            "NZDT": 0,
            "LTC": 0,
            "ETH": 0,
            "XMR": 0,
            "DOGE": 0,
            "ARBITRAGE_GAIN": 0.1,
            "PANIC_SELL": false,
            "RAGE_HAMMER": false,
            "COMPOUND": true,
            "MVTS": 0.00005,
            "bitRage_MODE": "crazybitch",
            "RT_ENABLED": true,
            "PANIC_BASE": "BTC",
            "CB_CHECK": false,
            "TAKE_PROFIT": true,
            "BNB_FEES": true,
            "DELETE_ON_SPREAD": 0.5,
            "PARALLEL_TRADES": false,
            "COMPOUND_BAGS": false
        }
```

## Defining pairs and overrides

In the `pairs` section of the config file you can add one or more pairs inside a block specifying the exchange the pairs will run on. 

When no pairs are specified for an exchange, bitRage will run in autoscan mode on this exchange, trading every possible pair for which you have set a base balance higher than 0.

Each pair must be assigned an existing strategy.

```text
todo
```

The override section allows for pair specific modifications to the assigned strategy. Any strategy parameter can be used as an override.

In the example above the pair will run the `bitrage` strategy, with a `BTC` allocation different than  defined in the strategy itself.


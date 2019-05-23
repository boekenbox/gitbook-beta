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
            "masterkey": "registered_api_key",
            "mastersecret": "secret_for_registered_api_key",
            "key": "trading_api_key",
            "secret": "secret_for_trading_api_key",
            "delay": 1,
            "type": "binance"
        },
```

Note that you can use a different API key for trading than the registered key. If you don't use a secondary key, you can just enter the registered key in the `key` parameter.

## Strategies

A strategy is defined in the `strategies` section of the config file. This strategy can then be assigned to one or more trading pairs.

**tbd**

It looks like this:

```text
"bitrage": {
            "BTC": 0.1,
            "USDT": 200,
            "USD": 200,
            "EUR": 200,
            "NZDT": 200,
            "LTC": 1,
            "ETH": 1,
            "XMR": 1,
            "DOGE": 50000,
            "BNB": 1,
            "GBP": 50,
            "ARBITRAGE_GAIN": 1,
            "TRADING_FEES": 0.75,
            "PANIC_SELL": false,
            "CHECK_SECOND": false,
            "CHECK_THIRD": false,
            "RAGE_HAMMER": true,
            "NO_BAGS": false,
            "COMPOUND": true,
            "BNB_FEES": false
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


---
description: 'Adding trading pairs to Gunbot, information about how cycling works.'
---

# Trading pairs

To configure which trading pairs Gunbot should trade, go to **Pairs** or **Easy edit**.

You can use an unlimited number of trading pairs, across multiple exchanges.

{% page-ref page="pair-processing.md" %}



## Add trading pairs

![](https://raw.githubusercontent.com/boekenbox/gitbook-images/master/image%20%2846%29.png)

Gunbot uses a standardized format for entering trading pairs, this allows you to use the same syntax for all exchanges you might use.

The format is: **BASECOIN-QUOTECOIN**, where the base coin is the one used to buy another asset. Be aware that some exchange show pair names in the exact reverse order.

To start trading on a new pair, just enter the pair name, pick the exchange and strategy and hit the **Add** button. When you want to temporarily stop trading a pair, use the **Enabled** toggle to disable the pair.

{% hint style="info" %}
### Pair naming conventions

Gunbot normalizes pair notation, where possible it uses this notation: BASECOIN-QUOTECOIN

All pairs with BTC as base currency are written like: BTC-ETH, BTC-OK, BTC-XLM

All pairs with USDT as base currency are written like: USDT-BTC, USDT-ETH, USDT-XMR
{% endhint %}



### Pair naming exceptions

On **Binance**, use YOYOW instead of YOYO.

For a few coins on **Bitfinex**, the API display name is required. These are: IOTA = IOT, DASH = DSH, QTUM = QTM, DATA = DAT, QASH = QSH

**Kraken** calls Bitcoin XBT, use BTC instead.

Pairs on **Bitmex** use almost the same symbols as on Bitmex itself, but with a hyphen-minus between the two asset names. Example: XBT-USD

Pairs on **Kraken Futures** follow the following conventions:

* Perpetual contracts: XBT-USD, ETH-USD, LTC-USD, etc.
* Monthly futures: XBT-MONTH, ETH-MONTH, LTC-MONTH, etc
* Quarterly futures: XBT-QUART, ETH-QUART, LTC-QUART, etc

Pairs on **Okex Futures** use the same notation as on their site, with hyphens in between the different parts of the pair. Example: USD-BTC-200417

## Override settings

Overrides are pair specific settings, overruling the assigned strategy. Every strategy parameter can be used as an override.

![](https://raw.githubusercontent.com/boekenbox/gitbook-images/master/image%20%2845%29.png)

You can use this, for example, to set a different trading limit for a specific pair.

When adding overrides, you can choose from a list of all available strategy settings. 

{% hint style="info" %}
Make sure to only add overrides for settings that actually have a function for the buy and sell methods of your strategy. See the strategy pages for detailed info about relevant settings.
{% endhint %}


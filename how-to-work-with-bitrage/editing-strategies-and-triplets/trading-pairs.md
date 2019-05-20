# Triplets / pairs

You define the trading pairs to monitor for arbitrage opportunities. Since bitRage is based on triangular arbitration, "pairs" are often referred to as "triplets" and consist of a combination of three individual trading pairs. 

Example of a valid triplet: BTC-ETC &gt; ETH-ETC &gt; BTC-ETH

| Pair | Trades \(normal mode\) |
| :--- | :--- |
| BTC-ETC | Stage 1: buy ETC for BTC |
| ETH-ETC | Stage 2: sell ETC for ETH |
| BTC-ETH | Stage 3: sell ETH for BTC |



To configure which trading pairs bitRage should trade, go to **Settings &gt; Trading &gt; Trading Pairs**.

![Triplets can be selected from a list.](../../.gitbook/assets/image%20%285%29.png)



You can use an unlimited number of trading pairs, across multiple exchanges.

**Pair processing example for 1 exchange:**

* TODO

{% hint style="info" %}
**Parallel processing of multiple exchanges**

If you have trading pairs across multiple exchanges, each exchange will process pairs in parallel. This means that a pair on exchange 1 does not wait for pairs on exchange 2 to be processed first.

Every exchange will individually cycle through enabled pairs like described above. Each exchange can have it's individual delay setting. TODO
{% endhint %}

## Add trading pairs

bitRage uses a standardized format for entering trading pairs, this allows you to use the same syntax for all exchanges you might use.

The format is: **BASECOIN-QUOTECOIN**, where the base coin is the one used to buy another asset. Be aware that some exchanges show pair names in the exact reverse order.



tbd



{% hint style="info" %}
**Pair naming conventions**

bitRage normalizes pair notation, all pairs for all exchanges follow the same logic: BASECOIN-QUOTECOIN

All pairs with BTC as base currency are written like: BTC-ETH, BTC-OK, BTC-XLM

All pairs with USDT as base currency are written like: USDT-BTC, USDT-ETH, USDT-XMR

**Exceptions**

For a few coins on Bitfinex, the API display name is required. These are:

IOTA = IOT, DASH = DSH, QTUM = QTM, DATA = DAT, QASH = QSH

Kraken calls Bitcoin XBT, use BTC instead.
{% endhint %}



## Override settings

Overrides are pair specific settings, overruling the assigned strategy. Every strategy parameter can be used as an override.

tbd


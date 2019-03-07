# Confirming indicators

To further restrict trading criteria for your strategy, you can use a number of confirming indicators for regular buy and sell orders. This page describes all settings options available for confirming indicators.

Orders are placed when both the main strategy settings and confirming indicators meet the market situation. When TrailMe is used too, it must finish trailing while other conditions meet. All these conditions must occur in the same cycle.

Especially when TrailMe is used together with confirming indicators, it makes sense to not set the indicators too strict as all order criteria must happen in the same cycle for an order to be placed \(strategy conditions + indicator conditions + hitting trailing stop\).

{% hint style="success" %}
**Indicators in Gunbot are calculated with live data.** 

For example for a 14 period RSI calculation, that means that the period close values for the past 13 completed candles are used, plus the live data for the current cycle.
{% endhint %}

{% hint style="info" %}
For margin trading, the buy side for indicator settings apply for opening long position. The sell side applies for opening short positions.
{% endhint %}



## ADX



## BTC PND protection



## EMA Spread



## MFI



## RSI



## Stochastic



## StochRSI



## Advanced settings



## Bollinger Bands for DCA



## Renko candles

![](https://user-images.githubusercontent.com/2372008/51115276-13a69500-1808-11e9-85b9-b221ef2cddeb.png)

[Renko](%20https://www.tradingview.com/wiki/Renko_Charts) candles can be used with the ichimoku-margin strategy.










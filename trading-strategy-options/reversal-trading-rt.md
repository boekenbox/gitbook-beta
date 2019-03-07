# Reversal trading \(RT\)

Reversal trading \(RT\) is a Gunbot technique to keep on trading profitably when prices move downwards after an asset has been purchased.

The principle is to use the already invested amount of base currency to accumulate more units of the quote currency after prices have moved downwards. When prices keep going down, or go sideways at a lower level than the initial purchase, RT can keep accumulating until prices move up enough to sell the accumulated amount for an overall profit.

Trading fees paid while in reversal trading are all accounted for.

![](https://user-images.githubusercontent.com/2372008/38331646-13c489aa-3854-11e8-95b4-8b9143edf69b.PNG)

_Note that this example is kept simple intentionally. Prices don't have to go straight down for RT to successfully accumulate._

\_\_

## How it works

Reversal trading starts when the current price is a set percentage lower than the last bought price, this is defined with `RT_GAIN`. The initial bag gets sold for base currency \(RT\_SELL\) and the invested amount is reserved for buying back more units when prices drop further. When the price then drops by a percentage defined with `RT_BUY_LEVEL`, quote currency gets bought \(RT\_BUY\). You now own more quote currency than you initially bought, at a lower price per unit.

This process will repeat when prices keep dropping, enabling you to keep accumulating quote currency without investing additional assets. Required funds are locked for the pair in reversal trading, and can't be used by other pairs.

With `TM_RT_SELL`, or when using `bb` as selling strategy, it's possible to place an RT\_SELL at a higher rate than the previous RT\_BUY, enabling you to reach a profitable exit point much faster.

When prices reach an overall profitable price \(EXIT POINT\), a normal sell order is placed using the sell criteria of your strategy.

In case prices recover to the break even point before an RT\_BUY could be made, the initial bag will be bought back to continue normal trading \(RT\_BUYBACK\). Alternatively, you can set a custom level for buying back quote with `RT_BUY_UP_LEVEL`.

**The exact process for reversal trading is dependent on the strategies used for buying or selling. There are slight differences described in detail below.**

\*\*\*\*

{% hint style="warning" %}
**Warnings**

* Do not activate reversal trading on existing bags that are already down a lot unless you use`TM_RT_SELL`! The decision to run reversal trading or not should best be made before you start trading a pair, this way the process can kick in timely.
* Reversal trading math is done based on your trading history, if your last sell order was at loss \(and not caused by stop limit\), reversal trading would immediately start when you enable it and continues until it manages to profitably end the RT cycle - even when you've disabled RT again. To prevent unwanted reversal trading, make sure to either have a profitable last sell order or to have set `IGNORE_TRADES_BEFORE` at a time after your last sell order at loss. To be sure, delete the pairs state JSON file after setting `IGNORE_TRADES_BEFORE`. Alternatively, you can set a maximum price difference between current price and average bought price with `RT_MAXBAG_PROTECTION`, to prevent RT from starting on pairs that already lost a lot of value.
{% endhint %}

\*\*\*\*

## RT flowcharts

There are three different ways Gunbot handles reversal trading, based on main strategies used for a pair. The chosen buy strategy affects the way RT\_BUY orders are executed, the sell strategy affects RT\_SELL orders.

Optional steps in the flowcharts are only relevant when `TM_RT_SELL` and/or `RT_TREND_ENABLED` are enabled.

####  

### 1. Simplified flow for RT

![](https://user-images.githubusercontent.com/2372008/47076714-a5016d80-d1ff-11e8-9c5e-5d12b2a7e3e6.PNG)

_This flowchart shows the basic steps for reversal trading, not considering additional options like trailing or strategy specific conditions._

####  

### 2. RT process for all strategies except `bb`

![](https://user-images.githubusercontent.com/2372008/47029958-02001380-d16d-11e8-8f7d-9f146fbbf24b.PNG)

####  

### 3. RT process for `bb`

 

![](https://user-images.githubusercontent.com/2372008/47029957-02001380-d16d-11e8-8cd6-f661deadf73d.PNG)

_`LOW_BB`/`HIGH_BB` in reversal trading use the same settings as with regular trading on `bb`._

\_\_

## Relevant settings

Following settings options are available for reversal trading.







Reversal trading depends on several TrailMe settings to reach better entry points for RT\_BUY and to make RT\_SELL\_UP work. The relevant settings are listed below.








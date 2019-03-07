# Bollinger Bands

This page describes how margin trading on Bitmex works with the Bollinger Bands strategy. The triggers for trades are slightly different than in the same strategy for regular trading.



## How to work with this strategy

{% hint style="info" %}
Using `bb` \(margin\) is only meaningful with `MEAN_REVERSION` enabled. 

The info below assumes you have set this.
{% endhint %}

The expected behavior for margin trading with Gunbot is that it will open one position, either long or short, and close this position when the target is reached. When the stop is hit before profitably closing a trade, Gunbot will place a stop order at loss. After closing a position, Gunbot will again look to open a new long or short position. Gunbot will not add to existing open positions.

Please don't manually add to or reduce positions opened by Gunbot, unless you stop running Gunbot on this trading pair until you've closed this position.

The examples below show how the basic triggers for `bb` work. Additionally, you can use confirming indicators and settings like ROE trailing.

### Long

![](https://user-images.githubusercontent.com/2372008/53409188-a4a08c80-39c0-11e9-8a8a-d5b8941985e4.png)

* A long position is opened when the ask price is below `LOW_BB` and `LONG_LEVEL`. In the example above `LOW_BB` would be set to 0, which represents the actual lower Bollinger Band. With different values you could set a target above \(positive value\) or below \(negative value\) the lower band.
* Position is closed when the desired `ROE` \(return on equity\) is reached. This is a percentage from the entry point, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `ROE`: 1.
* A position is closed at loss when `STOP_LIMIT` is reached. This is a percentage from the entry point in the opposite direction of your profit target, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `STOP_LIMIT`: 1.

 

### Short

![](https://user-images.githubusercontent.com/2372008/53412737-7162fb00-39ca-11e9-94d3-3963512f3a56.png)

* A short position is opened when the bid price is above `HIGH_BB` and `SHORT_LEVEL`. In the example above `HIGH_BB` would be set to 0, which represents the actual upper Bollinger Band. With different values you could set a target below \(positive value\) or above \(negative value\) the upper band.
* Position is closed when the desired `ROE` \(return on equity\) is reached. This is a percentage from the entry point, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `ROE`: 1.
* A position is closed at loss when `STOP_LIMIT` is reached. This is a percentage from the entry point in the opposite direction of your profit target, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `STOP_LIMIT`: 1.

## Strategy parameters

Following settings options are available for `bb` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `bb`. Accepted values are all strategy names as listed [here](https://github.com/GuntharDeNiro/BTCT/wiki/About-Gunbot-strategies).



## Margin settings

Margin settings control settings like leverage and the target for ROE. These parameters are relevant when using `bb` as buy and/or sell method.



## Buy settings

Buy settings are the primary trigger for opening long positions. These parameters control the execution of buy orders when using `bb` as buy method.



## Sell settings

Sell settings are the primary trigger for opening short positions. These parameters control the execution of sell orders when using `bb` as sell method.





## Indicator settings

Relevant indicators for trading with bb.

These settings have a direct effect on trading with `bb`, this is where you configure how Bollinger Bands are calculated and at which distance from them orders should be placed. Additionally, `BUY_LEVEL` is dependent on EMA.







#### Placeholders

The following parameters in `config.js` have no function for this strategy and act as placeholder.

| Parameter | Description |
| :--- | :--- |
| `ATRX` | Placeholder. |
| `ATR_PERIOD` | Placeholder. |
| `BUYLVL1` | Placeholder. |
| `BUYLVL2` | Placeholder. |
| `BUYLVL3` | Placeholder. |
| `BUYLVL` | Placeholder. |
| `BUY_LEVEL` | Placeholder. |
| `BUY_RANGE` | Placeholder. |
| `DISPLACEMENT` | Placeholder. |
| `DOUBLE_CHECK_GAIN` | Placeholder. |
| `FAST_SMA` | Placeholder. |
| `GAIN` | Placeholder. |
| `ICHIMOKU_PROTECTION` | Placeholder. |
| `KIJUN_BUY` | Placeholder. |
| `KIJUN_CLOSE` | Placeholder. |
| `KIJUN_PERIOD` | Placeholder. |
| `KIJUN_SELL` | Placeholder. |
| `KIJUN_STOP` | Placeholder. |
| `KUMO_BUY` | Placeholder. |
| `KUMO_CLOSE` | Placeholder. |
| `KUMO_SELL` | Placeholder. |
| `KUMO_SENTIMENTS` | Placeholder. |
| `KUMO_STOP` | Placeholder. |
| `MACD_LONG` | Placeholder. |
| `MACD_SHORT` | Placeholder. |
| `MACD_SIGNAL` | Placeholder. |
| `PP_BUY` | Placeholder. |
| `PP_SELL` | Placeholder. |
| `RENKO_ATR` | Placeholder. |
| `RENKO_BRICK_SIZE` | Placeholder. |
| `RENKO_PERIOD` | Placeholder. |
| `SELLLVL1` | Placeholder. |
| `SELLLVL2` | Placeholder. |
| `SELLLVL3` | Placeholder. |
| `SELLLVL` | Placeholder. |
| `SELL_RANGE` | Placeholder. |
| `SENKOUSPAN_PERIOD` | Placeholder. |
| `SLOW_SMA` | Placeholder. |
| `TAKE_BUY` | Placeholder. |
| `TBUY_RANGE` | Placeholder. |
| `TENKAN_BUY` | Placeholder. |
| `TENKAN_CLOSE` | Placeholder. |
| `TENKAN_PERIOD` | Placeholder. |
| `TENKAN_SELL` | Placeholder. |
| `TENKAN_STOP` | Placeholder. |
| `TP_PROFIT_ONLY` | Placeholder. |
| `TP_RANGE` | Placeholder. |
| `TSSL_TARGET_ONLY` | Placeholder. |
| `USE_RENKO` | Placeholder. |








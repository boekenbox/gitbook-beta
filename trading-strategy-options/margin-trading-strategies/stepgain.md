# Stepgain

This page describes how margin trading on Bitmex works with the Stepgain strategy. The triggers for trades are slightly different than in the same strategy for regular trading.



### How to work with this strategy

{% hint style="info" %}
Using `stepgain` \(margin\) is only meaningful with `MEAN_REVERSION` enabled. 

The info below assumes you have set this.
{% endhint %}

The expected behavior for margin trading with Gunbot is that it will open one position, either long or short, and close this position when the target is reached. When the stop is hit before profitably closing a trade, Gunbot will place a stop order at loss. After closing a position, Gunbot will again look to open a new long or short position. Gunbot will not add to existing open positions.

Please don't manually add to or reduce positions opened by Gunbot, unless you stop running Gunbot on this trading pair until you've closed this position.

### Long / Buy

A long position is opened when price is between your stepgain buy levels and changes direction while being below `LONG_LEVEL`.

### Short / Sell

A short position is opened when price is between your stepgain sell levels and changes direction while being above `SHORT_LEVEL`.

### Close

A position is closed when the desired `ROE` is reached.

### Stop

A position is closed at loss when `STOP_LIMIT` is reached.

 

## Strategy parameters

Following settings options are available for `stepgain` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `stepgain`. Accepted values are all strategy names as listed [here](https://github.com/GuntharDeNiro/BTCT/wiki/About-Gunbot-strategies).

 

## Margin settings

Margin settings control settings like leverage and the target for ROE. These parameters are relevant when using `stepgain` as buy and/or sell method.













## Placeholders

The following parameters in `config.js` have no function for this strategy and act as placeholder.

| Parameter | Description |
| :--- | :--- |
| `ATRX` | Placeholder. |
| `ATR_PERIOD` | Placeholder. |
| `BUY_LEVEL` | Placeholder. |
| `BUY_LEVEL` | Placeholder. |
| `BUY_RANGE` | Placeholder. |
| `DISPLACEMENT` | Placeholder. |
| `DOUBLE_CHECK_GAIN` | Placeholder. |
| `FAST_SMA` | Placeholder. |
| `GAIN` | Placeholder. |
| `GAIN` | Placeholder. |
| `HIGH_BB` | Placeholder. |
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
| `LOW_BB` | Placeholder. |
| `MACD_LONG` | Placeholder. |
| `MACD_SHORT` | Placeholder. |
| `MACD_SIGNAL` | Placeholder. |
| `PP_BUY` | Placeholder. |
| `PP_SELL` | Placeholder. |
| `RENKO_ATR` | Placeholder. |
| `RENKO_BRICK_SIZE` | Placeholder. |
| `RENKO_PERIOD` | Placeholder. |
| `RT_BUY_LEVEL` | Placeholder. |
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




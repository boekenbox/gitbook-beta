# Pingpong

This page describes how margin trading on Bitmex works with the PingPong strategy. The triggers for trades are slightly different than in the same strategy for regular trading.



## How to work with this strategy

The expected behavior for margin trading with Gunbot is that it will open one position, either long or short, and close this position when the target is reached. When the stop is hit before profitably closing a trade, Gunbot will place a stop order at loss. After closing a position, Gunbot will again look to open a new long or short position. Gunbot will not add to existing open positions.

Please don't manually add to or reduce positions opened by Gunbot, unless you stop running Gunbot on this trading pair until you've closed this position.

The examples below show how the basic triggers for `pp` work. Additionally, you can use confirming indicators and settings like ROE trailing.

### Long \(regular: trend following\)

![](https://user-images.githubusercontent.com/2372008/53484739-c5321a80-3a84-11e9-8533-19b39b9f5e89.png)

* A long position is opened when the ask price is equal to or above `PP_BUY`.
* Position is closed when the desired `ROE` \(return on equity\) is reached. This is a percentage from the entry point, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `ROE`: 1.
* A position is closed at loss when `STOP_LIMIT` is reached. This is a percentage from the entry point in the opposite direction of your profit target, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `STOP_LIMIT`: 1.

### Short \(regular: trend following\)

![](https://user-images.githubusercontent.com/2372008/53487073-cfefae00-3a8a-11e9-92c8-329ef27e0aa5.png)

* A short position is opened when the bid price is equal to or below `PP_SELL`.
* Position is closed when the desired `ROE` \(return on equity\) is reached. This is a percentage from the entry point, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `ROE`: 1.
* A position is closed at loss when `STOP_LIMIT` is reached. This is a percentage from the entry point in the opposite direction of your profit target, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `STOP_LIMIT`: 1.

### Long \(mean reversion mode\)

In `MEAN_REVERSION` mode the behavior for `PP_BUY` and `PP_SELL` is reversed in this strategy.

![](https://user-images.githubusercontent.com/2372008/53483654-3f14d480-3a82-11e9-986f-98d2cb74bd2f.png)

* A long position is opened when the ask price is equal to or below `PP_BUY`.
* Position is closed when the desired `ROE` \(return on equity\) is reached. This is a percentage from the entry point, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `ROE`: 1.
* A position is closed at loss when `STOP_LIMIT` is reached. This is a percentage from the entry point in the opposite direction of your profit target, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `STOP_LIMIT`: 1.

### Short \(mean reversion mode\)

In `MEAN_REVERSION` mode the behavior for `PP_BUY` and `PP_SELL` is reversed in this strategy.

![](https://user-images.githubusercontent.com/2372008/53487369-b8fd8b80-3a8b-11e9-996a-26ba327902f1.png)

* A short position is opened when the bid price is equal to or above `PP_SELL`.
* Position is closed when the desired `ROE` \(return on equity\) is reached. This is a percentage from the entry point, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `ROE`: 1.
* A position is closed at loss when `STOP_LIMIT` is reached. This is a percentage from the entry point in the opposite direction of your profit target, not taking leverage into consideration. Regardless what leverage is used, 1% price difference from your entry equals `STOP_LIMIT`: 1.

###  

## Strategy parameters

Following settings options are available for `pp` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `pp`. Accepted values are all strategy names as listed [here](https://github.com/GuntharDeNiro/BTCT/wiki/About-Gunbot-strategies).

####  

## Margin settings

Margin settings control settings like leverage and the target for ROE. These parameters are relevant when using `pp` as buy and/or sell method.







## Placeholders

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
| `BUY_LEVEL` | Placeholder. |
| `BUY_RANGE` | Placeholder. |
| `DISPLACEMENT` | Placeholder. |
| `DOUBLE_CHECK_GAIN` | Placeholder. |
| `FAST_SMA` | Placeholder. |
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
| `LONG_LEVEL` | Placeholder. |
| `LOW_BB` | Placeholder. |
| `MACD_LONG` | Placeholder. |
| `MACD_SHORT` | Placeholder. |
| `MACD_SIGNAL` | Placeholder. |
| `RENKO_ATR` | Placeholder. |
| `RENKO_BRICK_SIZE` | Placeholder. |
| `RENKO_PERIOD` | Placeholder. |
| `SELLLVL1` | Placeholder. |
| `SELLLVL2` | Placeholder. |
| `SELLLVL3` | Placeholder. |
| `SELLLVL` | Placeholder. |
| `SELL_RANGE` | Placeholder. |
| `SENKOUSPAN_PERIOD` | Placeholder. |
| `SHORT_LEVEL` | Placeholder. |
| `SLOW_SMA` | Placeholder. |
| `TAKE_BUY` | Placeholder. |
| `TAKE_BUY` | Placeholder. |
| `TAKE_PROFIT` | Placeholder. |
| `TBUY_RANGE` | Placeholder. |
| `TBUY_RANGE` | Placeholder. |
| `TENKAN_BUY` | Placeholder. |
| `TENKAN_CLOSE` | Placeholder. |
| `TENKAN_PERIOD` | Placeholder. |
| `TENKAN_SELL` | Placeholder. |
| `TENKAN_STOP` | Placeholder. |
| `TP_PROFIT_ONLY` | Placeholder. |
| `TP_PROFIT_ONLY` | Placeholder. |
| `TP_RANGE` | Placeholder. |
| `TP_RANGE` | Placeholder. |
| `TSSL_TARGET_ONLY` | Placeholder. |
| `USE_RENKO` | Placeholder. |




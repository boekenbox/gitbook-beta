# ATRTS

The Average True Range \([ATR](http://stockcharts.com/school/doku.php?id=chart_school:technical_indicators:average_true_range_atr)\) is an indicator that measures volatility. This strategy uses ATR to calculate trailing stops to provide buy and sell signals when volatility increases or decreases and crosses the trailing stop.

Using the configurable `ATRX` multiplier for ATR, a lower and upper limit are calculated.

* The lower limit, called ATR short, is calculated by substracting the result of `ATRX` from next rounds bid.
* The upper limit, called ATR long, is calculated by adding the result of `ATRX` to next rounds ask.

A buy order is placed when the ask price crosses up ATR long.

A sell order is placed when the bid price crosses under ATR short and price is above the break-even point.

As ATR does not provide information about price direction, it is strongly recommended to use an additional momentum indicator like RSI.



## Trading example

![](https://user-images.githubusercontent.com/2372008/47224087-f99d1800-d3ba-11e8-8f67-2f611244769b.PNG)

 _Example of how trading with this strategy can perform._ [_Details and settings_](https://www.tradingview.com/chart/BQXBTC/CGLIN3ce-ATRTS-Gunbot-trading-strategy/)

### 

## Strategy parameters

Following settings options are available for `ATRTS` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `ATRTS`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md).









## Placeholders

The following parameters in `config.js` have no function for this strategy and act as placeholder.

| Parameter | Description |
| :--- | :--- |
| `BUYLVL1` | Placeholder. |
| `BUYLVL2` | Placeholder. |
| `BUYLVL3` | Placeholder. |
| `BUYLVL` | Placeholder. |
| `BUY_RANGE` | Placeholder. |
| `DISPLACEMENT` | Placeholder. |
| `FAST_SMA` | Placeholder. |
| `GAIN` | Placeholder. |
| `HIGH_BB` | Placeholder. |
| `ICHIMOKU_PROTECTION` | Placeholder. |
| `KIJUN_CLOSE` | Placeholder. |
| `KIJUN_PERIOD` | Placeholder. |
| `KIJUN_STOP` | Placeholder. |
| `KUMO_CLOSE` | Placeholder. |
| `KUMO_SENTIMENTS` | Placeholder. |
| `KUMO_STOP` | Placeholder. |
| `LEVERAGE` | Placeholder. |
| `LONG_LEVEL` | Placeholder. |
| `LOW_BB` | Placeholder. |
| `MACD_LONG` | Placeholder. |
| `MACD_SHORT` | Placeholder. |
| `MACD_SIGNAL` | Placeholder. |
| `MAKER_FEES` | Placeholder. |
| `MEAN_REVERSION` | Placeholder. |
| `PP_BUY` | Placeholder. |
| `PP_SELL` | Placeholder. |
| `PRE_ORDER_GAP` | Placeholder. |
| `PRE_ORDER` | Placeholder. |
| `RENKO_ATR` | Placeholder. |
| `RENKO_BRICK_SIZE` | Placeholder. |
| `RENKO_PERIOD` | Placeholder. |
| `ROE_CLOSE` | Placeholder. |
| `ROE_LIMIT` | Placeholder. |
| `ROE_TRAILING` | Placeholder. |
| `ROE` | Placeholder. |
| `SELLLVL1` | Placeholder. |
| `SELLLVL2` | Placeholder. |
| `SELLLVL3` | Placeholder. |
| `SELLLVL` | Placeholder. |
| `SELL_RANGE` | Placeholder. |
| `SENKOUSPAN_PERIOD` | Placeholder. |
| `SHORT_LEVEL` | Placeholder. |
| `SLOW_SMA` | Placeholder. |
| `TENKAN_CLOSE` | Placeholder. |
| `TENKAN_PERIOD` | Placeholder. |
| `TENKAN_STOP` | Placeholder. |
| `TSSL_TARGET_ONLY` | Placeholder. |
| `USE_RENKO` | Placeholder. |


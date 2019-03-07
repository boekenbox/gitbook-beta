# Stepgain

Stepgain follows the markets prices and trend, and buys or sells as soon as the trend reverses. Assuming a trend reversal \(from downtrend to uptrend\) usually takes place close to the bottom of a price movement, this allows you to buy shortly after a price bottomed. Similarly, selling takes place when an uptrend turns into a downtrend.

Buying with Stepgain is based on [EMA](https://en.wikipedia.org/wiki/Moving_average#Exponential_moving_average), enabling Gunbot to start looking for a trend reversal after a set percentage below the lowest EMA is reached.

Trends are calculated automatically by XTrend and are visible in your logs. XTrend results can vary depending on your setting for `PERIOD`. Using XTrend is optional, you can also have stepgain trigger purely on price reversals above/below the configured level.

You can optionally use indicators like RSI or Stochastic as confirmation to only buy or sell when both a trend reversal and a specific indicator level occur.



## Trading example

![](https://user-images.githubusercontent.com/2372008/47218318-a66f9900-d3ab-11e8-858c-e4d2959a7371.PNG)

_Example of how trading with the stepgain strategy can perform._ [_Details and settings_](https://www.tradingview.com/chart/XLMBTC/SxHYdOCD-Stepgain-Gunbot-trading-strategy/)



## How to work with this strategy

The infographic below describes what triggers trades with this strategy.

![](https://user-images.githubusercontent.com/2372008/40718216-8e63121c-640f-11e8-917d-719104990195.PNG)

_In this example both BUYLVL and SELLLVL would be set to 2. A change of price movement direction is assumed a trend reversal in this example, in reality not every change of price direction will be considered a trend reversal because the strength of the trend is considered as well._

\_\_

## Strategy parameters

Following settings options are available for `stepgain` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `stepgain`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods).







## Placeholders

The following parameters in `config.js` have no function for this strategy and act as placeholder.

| Parameter | Description |
| :--- | :--- |
| `ATRX` | Placeholder. |
| `ATR_PERIOD` | Placeholder. |
| `BUY_LEVEL` | Placeholder. |
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
| `RT_BUY_LEVEL` | Placeholder. |
| `SELL_RANGE` | Placeholder. |
| `SENKOUSPAN_PERIOD` | Placeholder. |
| `SHORT_LEVEL` | Placeholder. |
| `SLOW_SMA` | Placeholder. |
| `TENKAN_CLOSE` | Placeholder. |
| `TENKAN_PERIOD` | Placeholder. |
| `TENKAN_STOP` | Placeholder. |
| `TSSL_TARGET_ONLY` | Placeholder. |
| `USE_RENKO` | Placeholder. |


# EMA spread

This strategy is based on [EMA](https://en.wikipedia.org/wiki/Moving_average#Exponential_moving_average), enabling Gunbot to buy when prices start moving up - indicated by the spread between fast and slow EMA decreasing. Selling takes places when prices start moving down again, indicated by the spread decreasing again.

The spread is calculated each cycle by subtracting the lowest EMA value from the highest EMA.

To refine this strategy, other indicators are available to be used as confirmation for both buying and selling. For example you could have Gunbot buy when the EMA spread starts decreasing and RSI is below 30.

{% hint style="warning" %}
Gain protection is optional for this strategy. 

Be aware that this can lead to sell orders below your break-even point.
{% endhint %}



## Trading example

![](https://user-images.githubusercontent.com/2372008/47227785-f0647900-d3c3-11e8-9e93-f6b34007cf3e.PNG)

_Example of how trading with this strategy can perform._ [_Details and settings_](https://www.tradingview.com/chart/ICXUSDT/mqrfoQWe-Emaspread-Gunbot-trading-strategy/)_._

\_\_

## How to work with this strategy

The infographic below describes what triggers trades with this strategy.

![](https://user-images.githubusercontent.com/2372008/41104585-01701d7e-6a6c-11e8-9a99-33432958ce73.PNG)

 

## Strategy parameters

Following settings options are available for `EMASPREAD` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `EMASPREAD`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods).









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
| `BUY_RANGE` | Placeholder. |
| `DISPLACEMENT` | Placeholder. |
| `EMASPREAD` | Placeholder. |
| `FAST_SMA` | Placeholder. |
| `ICHIMOKU_PROTECTION` | Placeholder. |
| `HIGH_BB` | Placeholder. |
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


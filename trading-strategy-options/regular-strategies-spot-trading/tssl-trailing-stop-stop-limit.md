# Tssl \(trailing stop / stop limit\)

Set a range to trail for better entry or exit points, by following prices while they are moving down- or upwards. This way Gunbot won't trade while prices are still moving in the same direction.



## Trading example

![](https://user-images.githubusercontent.com/2372008/47219307-c3f23200-d3ae-11e8-9dff-a8222360efd3.PNG)

_Example of how trading with this strategy can perform._ [_Details and settings_](https://www.tradingview.com/chart/NEOUSDT/dHbKuj7Y-Trailing-Stop-Stop-Limit-Gunbot-trading-strategy/)



## How to work with this strategy

The infographics below describes what triggers trades with this strategy.

![](https://user-images.githubusercontent.com/2372008/40186558-b0a5f818-59f5-11e8-8566-307546866c61.PNG)

![](https://user-images.githubusercontent.com/2372008/40186557-b0887252-59f5-11e8-896b-849a5fed897f.png)

You can select an option to only sell at profit, to avoid the risk of a stop limit sell at loss while you're still in the initial range around bought price. This is called `TSSL_TARGET_ONLY`.

> Minimum profit = `tssl` - `SELL_RANGE`

You can optionally use additional indicators like RSI for extra confirmation on entry and exit points.



## Strategy parameters

Following settings options are available for `tssl` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an override at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `tssl`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods).







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
| `DISPLACEMENT` | Placeholder. |
| `FAST_SMA` | Placeholder. |
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
| `SENKOUSPAN_PERIOD` | Placeholder. |
| `SHORT_LEVEL` | Placeholder. |
| `SLOW_SMA` | Placeholder. |
| `TENKAN_CLOSE` | Placeholder. |
| `TENKAN_PERIOD` | Placeholder. |
| `TENKAN_STOP` | Placeholder. |
| `USE_RENKO` | Placeholder. |




# SMA cross

This strategy is based on [SMA](https://www.investopedia.com/terms/s/sma.asp), enabling Gunbot to buy when prices start moving up - indicated by fast SMA crossing over slow SMA. Selling takes place as soon as fast SMA crosses down slow SMA.

To refine this strategy, other indicators are available to be used as confirmation for both buying and selling. For example you could have Gunbot buy when slow SMA crosses up fast SMA and and RSI is below 30.

{% hint style="warning" %}
Gain protection is optional for this strategy. 

Be aware that this can lead to sell orders below your break-even point. 

Normal constraints like "buy once, sell once" don't apply to this strategy: each time buying criteria occur, Gunbot will place a buy order as high as set in your balance settings.
{% endhint %}



## Trading example

![](https://user-images.githubusercontent.com/2372008/47293427-6a863f00-d60a-11e8-9c26-0a5e9e2cf979.PNG)

 _Example of how trading with this strategy can perform._ [_Details and settings_](https://www.tradingview.com/chart/BTCUSDT/CuQ1RJzp-SMACROSS-Gunbot-trading-strategy/)



## How to work with this strategy

The infographic below describes what triggers trades with this strategy.

![](https://user-images.githubusercontent.com/2372008/41108606-4c435920-6a75-11e8-913a-07ef8e06a39a.png)

 

## Strategy parameters

Following settings options are available for `SMACROSS` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `SMACROSS`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods).







## Placeholders

The following parameters in `config.js` have no function for this strategy and act as placeholder.

| Parameter | Description |
| :--- | :--- |
| `ADX_ENABLED` | Placeholder. |
| `ATRX` | Placeholder. |
| `ATR_PERIOD` | Placeholder. |
| `BUYLVL1` | Placeholder. |
| `BUYLVL2` | Placeholder. |
| `BUYLVL3` | Placeholder. |
| `BUYLVL` | Placeholder. |
| `BUY_RANGE` | Placeholder. |
| `DISPLACEMENT` | Placeholder. |
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
| `TENKAN_CLOSE` | Placeholder. |
| `TENKAN_PERIOD` | Placeholder. |
| `TENKAN_STOP` | Placeholder. |
| `TSSL_TARGET_ONLY` | Placeholder. |
| `USE_RENKO` | Placeholder. |


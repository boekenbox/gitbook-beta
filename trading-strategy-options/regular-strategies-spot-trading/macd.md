# MACD

This strategy is based on [MACD](https://www.investopedia.com/terms/m/macd.asp), taking advantage of signals that indicate momentum is likely changing.

A buy order is placed when the MACD line crosses up the signal line, a sell order is placed when the MACD line crosses down the signal line.

To refine this strategy, other indicators are available to be used as confirmation for both buying and selling. For example you could have Gunbot buy on a bullish signal and RSI is 30 or lower.

{% hint style="warning" %}
Gain protection is optional for this strategy. 

Be aware that this can lead to sell orders below your break-even point. 

Normal constraints like "buy once, sell once" don't apply to this strategy: each time buying criteria occur, Gunbot will place a buy order as high as set in your balance settings.
{% endhint %}



### Trading example

![](https://user-images.githubusercontent.com/2372008/47229545-41766c00-d3c8-11e8-989f-67ab1b50b653.PNG)

_Example of how trading with this strategy can perform._ [_Details and settings_](https://www.tradingview.com/chart/ETHUSD/1mG1CbWo-MACD-Gunbot-trading-strategy/)



## How to work with this strategy

The infographic below describes what triggers trades with this strategy.

![](https://user-images.githubusercontent.com/2372008/41107283-5ba76206-6a72-11e8-88ef-ecf39e1ce953.PNG)

 

## Strategy parameters

Following settings options are available for `MACD` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `MACD`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods).









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


# Bollinger Bands \(TA\)

[Bollinger Bands](https://en.wikipedia.org/wiki/Bollinger_Bands) indicate relative high and low prices, using this information you can buy relatively low and sell relatively high.

With this strategy you can configure at which percentage from the lower Bollinger Band Gunbot should buy, and at which percentage from the upper Bollinger Band a sell order should be placed. Orders are placed after prices first move outside the set level, then move back in.

{% hint style="info" %}
Some extra features are available for users of Gunbot Standard edition and higher. These are marked below.
{% endhint %}

{% hint style="warning" %}
Gain protection is optional for this strategy. 

Be aware that this can lead to sell orders below your break-even point.
{% endhint %}



## Trading example

![](https://user-images.githubusercontent.com/2372008/47218852-65788400-d3ad-11e8-8100-1ab21cbc70dd.PNG)

 _Example of how trading with this strategy can perform._ [_Details and settings_](https://www.tradingview.com/chart/EOSUSDT/L6342dzc-Bollinger-Bands-TA-Gunbot-trading-strategy/)



## How to work with this strategy

The infographic below describes what triggers trades with this strategy.

![bollinger-bands-ta](https://user-images.githubusercontent.com/2372008/40925897-196d6510-681b-11e8-94ac-99757f46ab7b.PNG)

 

## Strategy parameters

Following settings options are available for `BBTA` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `BBTA`. Accepted values are all strategy names as listed [here.](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods)







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
| `ICHIMOKU_PROTECTION` | Placeholder. |
| `KIJUN_CLOSE` | Placeholder. |
| `KIJUN_PERIOD` | Placeholder. |
| `KIJUN_STOP` | Placeholder. |
| `KUMO_CLOSE` | Placeholder. |
| `KUMO_SENTIMENTS` | Placeholder. |
| `KUMO_STOP` | Placeholder. |
| `LEVERAGE` | Placeholder. |
| `LONG_LEVEL` | Placeholder. |
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


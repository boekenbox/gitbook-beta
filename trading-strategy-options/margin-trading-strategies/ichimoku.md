# Ichimoku

This page describes how margin trading on Bitmex works with the [ichimoku](https://github.com/GuntharDeNiro/BTCT/wiki/Ichimoku) strategy. The triggers for trades are slightly different than in the same strategy for regular trading.



## How to work with this strategy

The expected behavior for margin trading with Gunbot is that it will open one position, either long or short, and close this position when the target is reached. When the stop is hit before profitably closing a trade, Gunbot will place a stop order at loss. After closing a position, Gunbot will again look to open a new long or short position. Gunbot will not add to existing open positions.

Please don't manually add to or reduce positions opened by Gunbot, unless you stop running Gunbot on this trading pair until you've closed this position.

For this strategy it is recommended to use an additional momentum indicator to confirm long and short entries.

### Long / Buy

Before a long position is opened, one of the following conditions must occur to put Gunbot on "long alert":

1. The current candle crosses over Kumo. This means that all of open, close, high and low must be above Kumo.
2. Tenkan-sen crosses over Kijun-sen, above Kumo.

A long position is then opened when both of the following confirmations happens in a later cycle, they do not have to happen in the same cycle:

1. Chikou-span crosses over the "past Kumo" \(Kumo value of x periods ago, defined by `DISPLACEMENT`\).
2. The "future Kumo" is bullish/green \(Kumo value of x periods in the future, defined by `DISPLACEMENT`\).

### Short / Sell

Before a short position is opened, one of the following conditions must occur to put Gunbot on "short alert":

1. The current candle crosses below Kumo. This means that all of open, close, high and low must be below Kumo.
2. Tenkan-sen crosses under Kijun-sen, below Kumo.

A short position is then opened when both of the following confirmations happens in a later cycle, they do not have to happen in the same cycle:

1. Chikou-span crosses under the "past Kumo" \(Kumo value of x periods ago, defined by `DISPLACEMENT`\).
2. The "future Kumo" is bearish/red \(Kumo value of x periods in the future, defined by `DISPLACEMENT`\).

### Close

A long position is closed when the current candle crosses under Tenkan-sen, Kijun-sen or Kumo. This means that all of open, close, high and low must be below the selected item. Alternatively, you can set a ROE target for closing a position.

A short position is closed when the current candle crosses over Tenkan-sen, Kijun-sen or Kumo. This means that all of open, close, high and low must be above the selected item. Alternatively, you can set a ROE target for closing a position.

You can configure which of the three items is used for closing a position, with `TENKAN_CLOSE`, `KIJUN_CLOSE`, `KUMO_CLOSE` or `ROE_CLOSE`. If multiple of these parameters are set to true, the first of which occurs will close the position.

### Stop

A long position is stopped when the current candle crosses under Tenkan-sen, Kijun-sen or Kumo. This means that all of open, close, high and low must be above the selected item.

A short position is stopped when the current candle crosses over Tenkan-sen, Kijun-sen or Kumo. This means that all of open, close, high and low must be under the selected item.

You can configure which of the three items is used for stopping a position, with `TENKAN_STOP`, `KIJUN_STOP` or `KUMO_STOP`. If multiple of these parameters are set to true, the first of which occurs will close the position. Make sure to use different lines for closing and stopping a position.

After a stop is hit, the "alert" conditions for a long or short must happen again before another position is opened.



### Strategy parameters

Following settings options are available for `ichimoku` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an [override](https://github.com/GuntharDeNiro/BTCT/wiki/Gunbot-settings#overrides) at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `ichimoku`. Accepted values are all strategy names as listed [here](https://github.com/GuntharDeNiro/BTCT/wiki/About-Gunbot-strategies).

 

## Margin settings

Margin settings control settings like leverage and the target for ROE. These parameters are relevant when using `ichimoku` as buy and/or sell method.







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
| `BUY_RANGE` | Placeholder. |
| `DOUBLE_CHECK_GAIN` | Placeholder. |
| `FAST_SMA` | Placeholder. |
| `GAIN` | Placeholder. |
| `HIGH_BB` | Placeholder. |
| `ICHIMOKU_PROTECTION` | Placeholder. |
| `KIJUN_BUY` | Placeholder. |
| `KIJUN_SELL` | Placeholder. |
| `KUMO_BUY` | Placeholder. |
| `KUMO_SELL` | Placeholder. |
| `KUMO_SENTIMENTS` | Placeholder. |
| `LONG_LEVEL` | Placeholder. |
| `LOW_BB` | Placeholder. |
| `MACD_LONG` | Placeholder. |
| `MACD_SHORT` | Placeholder. |
| `MACD_SIGNAL` | Placeholder. |
| `MEAN_REVERSION` | Placeholder. |
| `PP_BUY` | Placeholder. |
| `PP_SELL` | Placeholder. |
| `SELLLVL1` | Placeholder. |
| `SELLLVL2` | Placeholder. |
| `SELLLVL3` | Placeholder. |
| `SELLLVL` | Placeholder. |
| `SELL_RANGE` | Placeholder. |
| `SHORT_LEVEL` | Placeholder. |
| `SLOW_SMA` | Placeholder. |
| `STOP_LIMIT` | Placeholder. |
| `TAKE_BUY` | Placeholder. |
| `TBUY_RANGE` | Placeholder. |
| `TENKAN_BUY` | Placeholder. |
| `TENKAN_SELL` | Placeholder. |
| `TP_PROFIT_ONLY` | Placeholder. |
| `TP_RANGE` | Placeholder. |
| `TSSL_TARGET_ONLY` | Placeholder. |


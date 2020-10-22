# Support / Resistance

Buy at support, sell at resistance. That's all this strategy does. You can configure a distance from support and resistance, to configure a range where it will trade.

## How to work with this strategy

There is just a single setting that defines the entry point for this strategy: `SupRes_SPREAD`

This setting represents a percentage \(of price\) above the first support level \(when buying\), or below the first resistance level \(when selling\). As soon as price crosses this threshold, it will place an order. If the balance settings allow for multiple orders, a buy order gets placed every time the buy conditions are met.

This setting represents a percentage \(of price\) above the first support level \(when buying\), or below the first resistance level \(when selling\). As soon as price crosses this threshold, it will place an order.

In the example below, `SupRes_SPREAD` is set to 0.1, the "buy at" line visualizes the target. The sell target would be 0.1 % below the first resistance level.

In the example below, `SupRes_SPREAD` is set to 0.1, the "buy at" line visualizes the target.

In the example below, `SupRes_SPREAD` is set to 0.1, the "buy at" line visualizes the target.

![](../../.gitbook/assets/image%20%2875%29.png)

Keep in mind that support and resistance are not static targets. This makes the `SupRes_SPREAD` setting more or less a trailing range. It's very important to set a value that makes sense for the current pair and the price range it is in: too big of a spread can cause immediate trades.

The strategy sells when price crosses `SupRes_SPREAD` and `GAIN` is reached.

This strategy can buy multiple times, it can be capped with `SupRes_MAX`.

### Formula

Gunbot uses the following formula to calculate support and resistance levels. The number of candles uses as input is user configurable with the `SMAPERIOD`setting.

```text
P = (H + L + C) / 3 
R1 = (P  2) - L 
R2 = P + (H - L) 
S1 = (P  2) - H 
S2 = P - (H - L)
```

{% hint style="success" %}
**Less options than usual**

This strategy is a bit different from other strategies, it has much less configurable options. Confirming indicators or additional trailing are disabled.
{% endhint %}



he Emotionless strategy is fully tuned and ready to use, even for novice traders! It's meant to be a relatively safe strategy, with modest but steady gains.

With this strategy, you don't need to think about setting the right or best parameters: it's all there already. You only need to set the basics like your trading limit and choose on which pairs you want to trade. Optionally, you can increase `GAIN` slightly.

The specifics for how this trading strategy exactly works will not be disclosed.

**Some extra features are available for users of Gunbot Standard edition and higher. These are marked below.**

![Chart showing actual trades by Emotionless. Each sell order gained ~0.6%](https://user-images.githubusercontent.com/2372008/44547052-27971080-a71a-11e8-8919-c47ecbfc54ef.png)

## Strategy parameters

Following settings options are available for `SupportResistance` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

Following settings options are available for `emotionless` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

Following settings options are available for `emotionless` and can be set in the strategy configurator of the GUI or the strategies section of the config.js file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an override at the pair level.

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `SupportResistance`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods).

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `emotionless`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods).

Using the `BUY_METHOD` and `SELL_METHOD` parameters you can combine different methods for buying and selling. This strategy page assumes both `BUY_METHOD` and `SELL_METHOD` are set to `emotionless`. Accepted values are all strategy names as listed [here](../about-gunbot-strategies/trading-methods.md#available-buy-and-sell-methods).

## Buy & sell settings

## Buy settings

## Buy settings

Buy settings are the primary trigger for buy orders. These parameters control the execution of buy orders when using `emotionless` as buy method.

### Buy enabled

{% tabs %}
{% tab title="Description" %}
Set this to false to prevent Gunbot from placing buy orders.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** true
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy buy | Strategy sell |
| DCA buy | Stop limit |
| RT buy | Close |
| RT buyback | RT sell |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `BUY_ENABLED`
{% endtab %}
{% endtabs %}

### Sell enabled

### Buy Level

{% tabs %}
{% tab title="Description" %}
Set this to false to prevent Gunbot from placing sell orders.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** true
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy sell | Strategy buy |
| Stop limit | RT buy |
| RT sell | RT buyback |
|  | Close |
|  | DCA buy |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `SELL_ENABLED`
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Description" %}
This sets the target for buying at a percentage below the lowest EMA.

When you set this to 1, the target for buy orders is 1% below the currently lowest EMA. Due to trailing, it is possible Gunbot will buy slightly higher than the target.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents a percentage.

**Default value:** 1
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy buy | Strategy sell |
|  | Stop limit |
|  | Close |
|  | RT sell |
|  | DCA buy |
|  | RT buy |
|  | RT buyback |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `BUY_LEVEL`
{% endtab %}
{% endtabs %}

### Sup / Res spread

### NBA

{% tabs %}
{% tab title="Description" %}
"Never Buy Above". Use this to only allow buy orders below the last sell rate.

This sets the minimum percentage difference between the last sell order and the next buy. The default setting of 0 disables this option.

When set to 1, Gunbot will only place a buy order when the strategy buy criteria meet and price is at least 1% below the last sell price.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents a percentage.

**Default value:** 0
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy buy | Strategy sell |
|  | Stop limit |
|  | Close |
|  | RT sell |
|  | DCA buy |
|  | RT buy |
|  | RT buyback |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `NBA`
{% endtab %}
{% endtabs %}

## Sell settings

Sell settings are the primary trigger for sell orders. These parameters control the execution of sell orders when using `emotionless` as sell method.

### Sell enabled

{% tabs %}
{% tab title="Description" %}
Set this to false to prevent Gunbot from placing sell orders.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** true
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy sell | Strategy buy |
| Stop limit | RT buy |
| RT sell | RT buyback |
|  | Close |
|  | DCA buy |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `SELL_ENABLED`
{% endtab %}
{% endtabs %}

### Gain

{% tabs %}
{% tab title="Description" %}
This sets the minimum target for selling. Gunbot will sell once price reaches the set percentage above the break-even point. and `SupRes_SPREAD` is reached.

If you want to have at least 2% profit per trade, set this to 2.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents a percentage.

**Default value:** 0.5
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy sell | Strategy buy |
|  | RT buy |
|  | RT buyback |
|  | RT sell |
|  | Close |
|  | DCA buy |
|  | Stop limit |
|  |  |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `GAIN`
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Description" %}
This sets the minimum target for selling. Gunbot will sell once price reaches the set percentage above the break-even point. and `HIGH_BB` is reached.

If you want to have at least 2% profit per trade, set this to 2.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents a percentage.

**Default value:** 0.5
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy sell | Strategy buy |
|  | RT buy |
|  | RT buyback |
|  | RT sell |
|  | Close |
|  | DCA buy |
|  | Stop limit |
|  |  |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `GAIN`
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Description" %}
This sets the minimum target for selling. Gunbot will sell once price reaches the set percentage above the break-even point. and `HIGH_BB` is reached.

If you want to have at least 2% profit per trade, set this to 2.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents a percentage.

**Default value:** 0.5
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy sell | Strategy buy |
|  | RT buy |
|  | RT buyback |
|  | RT sell |
|  | Close |
|  | DCA buy |
|  | Stop limit |
|  |  |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `GAIN`
{% endtab %}
{% endtabs %}

### Double Check Gain

{% tabs %}
{% tab title="Description" %}
This is an extra check that looks at your recent trading history to verify `GAIN` will be reached before placing a sell order.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** true
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy sell | Strategy buy |
|  | RT buy |
|  | RT buyback |
|  | RT sell |
|  | Close |
|  | DCA buy |
|  | Stop limit |
|  |  |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `DOUBLE_CHECK_GAIN`
{% endtab %}
{% endtabs %}

## Indicator settings

Relevant indicators for trading with emotionless.

These settings have a direct effect on trading with `SupportResistance`.

These settings have a direct effect on trading with `emotionless`.

These settings have a direct effect on trading with `emotionless`.

### Period

{% tabs %}
{% tab title="Description" %}
This sets the candlestick period used for trading, this affects all indicators within the strategy.

Only use [supported values](../../how-to-work-with-gunbot/basic-workings/period.md#supported-period-values).

Setting a short period allows you to trade on shorter trends, but be aware that these will be noisier than longer periods.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical– represents candlestick size in minutes.

**Default value:** 15
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy sell | RT buy |
| Strategy buy | RT buyback |
| DCA buy \(when using an indicator to trigger\) | RT sell |
|  | Close |
|  | Stop limit |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `PERIOD`
{% endtab %}
{% endtabs %}

### SMA Period

### Slow EMA

{% tabs %}
{% tab title="Description" %}
This defines the number of candles used for calculating support and resistance level.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents a number of candlesticks.

**Default value:** 50
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy sell | RT buy |
| Strategy buy | RT buyback |
|  | RT sell |
|  | Close |
|  | Stop limit |
|  | DCA buy order |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `SMAPERIOD`
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Description" %}
Set this to the amount of candlesticks you want to use for your slow EMA. The closing price for each candle is used in the slow EMA calculation.

For example: when you set `PERIOD` to 5, and want to use 2h for slow EMA – you need to set `EMA1` to 24 \(24 \* 5 mins\).
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents a number of candlesticks.

**Default value:** 16
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy buy | RT buy |
|  | RT buyback |
|  | RT sell |
|  | Close |
|  | Stop limit |
|  | Strategy sell |
|  | DCA buy |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `EMA1`
{% endtab %}
{% endtabs %}

### Medium EMA

{% tabs %}
{% tab title="Description" %}
Set this to the amount of candlesticks you want to use for your medium EMA. The closing price for each candle is used in the fast EMA calculation.

For example: when you set `PERIOD` to 5, and want to use 1h for medium EMA – you need to set `EMA2` to 12 \(12 \* 5 mins\).
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents a number of candlesticks.

**Default value:** 8
{% endtab %}

{% tab title="Order types" %}
| Affects | Does not affect |
| :--- | :--- |
| Strategy buy | RT buy |
|  | RT buyback |
|  | RT sell |
|  | Close |
|  | Stop limit |
|  | Strategy sell |
|  | DCA buy |
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `EMA2`
{% endtab %}
{% endtabs %}

## TrailMe settings

{% hint style="info" %}
This is not available for Gunbot Starter.
{% endhint %}



These settings can be used, but they are not tested and not intended for use with emotionless. Use at your own risk.


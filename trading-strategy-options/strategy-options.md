# Strategy options

Following settings options are available for `bitrage` and can be set in the strategy configurator of the GUI or the strategies section of the `config.json` file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an override at the pair level.



## Trading options

You can use a few different modes and options for executing trades, these are described below.

### bitRage Mode

{% tabs %}
{% tab title="Description" %}
This sets the mode for executing arbitrage opportunities.

In `crazybitch` mode, bitRage will execute trades for all three stages as fast as possible, for market rates. Optionally you can use an extra check if the third stage is still profitable before the final order is placed, this check is called `CB_CHECK`.

In `safe` mode, bitRage does not aim for immediate order execution. It will place subsequent limit orders for all three stages, each at profitable rates. When needed, these orders will be continuously cancelled when rates change more than set in `DELETE_ON_SPREAD` , and replaced at rates that have a higher chance of execution.
{% endtab %}

{% tab title="Values" %}
**Values:** string, available options: crazybitch, safe

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `bitRage_MODE`
{% endtab %}
{% endtabs %}

### Arbitrage Gain

{% tabs %}
{% tab title="Description" %}
Sets the minimum expected gain from an arbitrage opportunity, after fees.

When set to 1, bitRage will only enter opportunities that have an expected overall gain of 1%. 

Note that bitRage does not only check for expected gain before entering an opportunity, it will also check if there is enough expected trading volume.
{% endtab %}

{% tab title="Values" %}
**Values:** number, represents a percentage

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `ARBITRAGE_GAIN`
{% endtab %}
{% endtabs %}

### CB Check

{% tabs %}
{% tab title="Description" %}
Enables an additional check for stage three trades when using the `crazybitch` mode. 

The third trade only gets fired when the expected market price is still profitable after having executed the first two trades. If not, bitRage will wait with this order until a profitable rate is available.
{% endtab %}

{% tab title="Values" %}
**Values:** number, represents a percentage

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `CB_CHECK`
{% endtab %}
{% endtabs %}

### Take Profit

{% tabs %}
{% tab title="Description" %}
When enabled, bitRage will attempt to take any opportunity with an expected gain covering more than just the trading fees. This overrules `ARBITRAGE_GAIN`.
{% endtab %}

{% tab title="Values" %}
**Values:** number, represents a percentage

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `TAKE_PROFIT`
{% endtab %}
{% endtabs %}

### RT Enabled

{% tabs %}
{% tab title="Description" %}
This setting allows trading a reverse variant of a defined pair, often an RT opportunity will happen when no regular opportunity exists.

Example for a defined triple like BTC-ETC &gt; ETH-ETC &gt; BTC-ETH:

* In normal mode, bitRage will buy ETC with BTC in stage 1, sell ETC for ETH in stage 2, then sell ETH for BTC in stage 3.
* In RT mode, bitRage first buys ETH with BTC, then buys ETC with ETH and finally sells ETC for BTC.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `RT_ENABLED`
{% endtab %}
{% endtabs %}

### Rage Hammer

{% tabs %}
{% tab title="Description" %}
With this setting, after executing all three trades for an arbitrage opportunity, bitRage will check if there is still an opportunity on the same triplet. It will then immediately proceed trading on this triple until the opportunity is exhausted.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `RAGE_HAMMER`
{% endtab %}
{% endtabs %}

### Compound Bags

{% tabs %}
{% tab title="Description" %}
When enabled, bitRage will ignore previous balances and sell the complete balance for any coin in stage 3. Be aware that some triples sell BTC \(or other coins most used as primary base\) in stage 3, in that case all BTC would be sold.

In case you prefer bitRage to only work with the amounts obtained in stage 2, disable this option.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `COMPOUND_BAGS`
{% endtab %}
{% endtabs %}

### Parallel Trades

{% tabs %}
{% tab title="Description" %}
Use this setting to ensure the fastest trade execution time for opportunities in `crazybitch` mode.

Make sure to have balances in all involved base currencies when using this. 

{% hint style="info" %}
This setting is specific to websockets in crazybitch mode.
{% endhint %}
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `PARALLEL_TRADES`
{% endtab %}
{% endtabs %}

### Delete on Spread

{% tabs %}
{% tab title="Description" %}
Defines the maximum allowed price difference before a stage 1 or stage 2 order gets cancelled in safe mode. 

When set to 0.5, an open order will be cancelled when the best bid/ask price moves away more than 0.5% from the rate of your open order. After the order is cancelled, it will be replaced at current rates, if still profitable to do so.

{% hint style="info" %}
This setting is specific to safe mode.
{% endhint %}
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents a percentage

**Default value:** 0.5
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `DELETE_ON_SPREAD`
{% endtab %}
{% endtabs %}

## Balance settings

Available balances for trades are defined per base currency. Only set values for the base currencies you will trade, leave the rest set to 0 to disable them.

### BTC

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with BTC as base currency.

When set to 1, bitRage will enter an arbitrage opportunity up to 1 BTC. 
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `BTC`
{% endtab %}
{% endtabs %}

### USDT

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with USDT as base currency.

When set to 1000, bitRage will enter an arbitrage opportunity up to 1000 USDT. 
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `USDT`
{% endtab %}
{% endtabs %}

### USD

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with USD as base currency.

When set to 1000, bitRage will enter an arbitrage opportunity up to 1000 USD. 
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `USD`
{% endtab %}
{% endtabs %}

### EUR

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with EUR as base currency.

When set to 1000, bitRage will enter an arbitrage opportunity up to 1000 EUR. 
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `EUR`
{% endtab %}
{% endtabs %}

### NZDT

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with NZDT as base currency.

When set to 1000, bitRage will enter an arbitrage opportunity up to 1000 NZDT. 
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `NZDT`
{% endtab %}
{% endtabs %}

### LTC

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with LTC as base currency.

When set to 50, bitRage will enter an arbitrage opportunity up to 50 LTC.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `LTC`
{% endtab %}
{% endtabs %}

### ETH

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with ETH as base currency.

When set to 100, bitRage will enter an arbitrage opportunity up to 100 ETH. 
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `ETH`
{% endtab %}
{% endtabs %}

### XMR

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with XMR as base currency.

When set to 100, bitRage will enter an arbitrage opportunity up to 100 XMR. 
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `XMR`
{% endtab %}
{% endtabs %}

### DOGE

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with DOGE as base currency.

When set to 1000000, bitRage will enter an arbitrage opportunity up to 1000000 DOGE.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `DOGE`
{% endtab %}
{% endtabs %}

### BNB

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with BNB as base currency.

When set to 10000, bitRage will enter an arbitrage opportunity up to 10000 BNB. If the opportunity has less volume, the appropriate amount below the set limit will be used.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `EUR`
{% endtab %}
{% endtabs %}

### GBP

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with GBP as base currency.

When set to 1000, bitRage will enter an arbitrage opportunity up to 1000 GBP. If the opportunity has less volume, the appropriate amount below the set limit will be used.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** 0
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `GBP`
{% endtab %}
{% endtabs %}

### BNB Fees

{% tabs %}
{% tab title="Description" %}
Enable this when you trade on Binance and use BNB as fee currency.

This does not substitute setting a correct level of `TRADING_FEES` in the exchange section.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `BNB_FEES`
{% endtab %}
{% endtabs %}

### MVTS

{% tabs %}
{% tab title="Description" %}
Sets a threshold for sell orders lower than the exchange minimum trade size.

If you own less than the set amount, sell orders will not be placed and bitRage will wait for another arbitrage opportunity on the same triplet.

When trading a fiat pair like USDT-x, set a whole number like 10 as `MVTS`.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `MVTS`
{% endtab %}
{% endtabs %}

### Compound

{% tabs %}
{% tab title="Description" %}
When enabled, profits from previous trades get reinvested.

For example, when a BTC limit of 0.2 is set and over time 0.02 profits have been generated, bitRage will invest up to 0.22 BTC per arbitrage opportunity.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `COMPOUND`
{% endtab %}
{% endtabs %}

### Panic Base

{% tabs %}
{% tab title="Description" %}
This sets the target base currency when executing `PANIC_SELL`. All traded assets will be converted into the set currency.
{% endtab %}

{% tab title="Values" %}
**Values:** String, available options: BTC, USDT, USD, EUR, NZDT, LTC, ETH, XMR, DOGE, BNB, GBP

**Default value:** TODO
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `PANIC_BASE`
{% endtab %}
{% endtabs %}

### 








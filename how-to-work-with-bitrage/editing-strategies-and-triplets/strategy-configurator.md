# Strategy configurator

A strategy in bitRage is a collection of settings that can be assigned to one or more trading pairs. These pairs will then trade according to the assigned settings.

On **Settings &gt; Strategies &gt; Strategy Configurator** you can view and modify strategy presets, or create your own custom strategies.

## Create a new strategy

![](../../.gitbook/assets/image%20%2823%29.png)

Set a nickname for your strategy \(this can be anything you want\), and select the main methods for buying and selling. Hit the **Create** button to save the new strategy.

You can create an unlimited number of strategies.

## Modify an existing strategy

Click on a strategy nickname to edit its settings.

![](../../.gitbook/assets/image%20%2814%29.png)



## Strategy settings

Following settings options are available for `bitrage` and can be set in the strategy configurator of the GUI or the strategies section of the `config.json` file.

These settings are global and apply to all pairs running this strategy. When you want a specific parameter to be different for one or more pairs, use an override at the pair level.



## Balance settings

Available balances for trades are defined per base currency. Only set values for the base currencies you will trade, leave the rest set to 0 to disable them.

### BTC

{% tabs %}
{% tab title="Description" %}
Sets the maximum investment per trade for triplets with BTC as base currency.

When set to 1, bitRage will enter an arbitrage opportunity up to 1 BTC. If the opportunity has less volume, the appropriate amount below the set limit will be used.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical, represents an amount in base currency.

**Default value:** true
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `BTC`
{% endtab %}
{% endtabs %}

### 


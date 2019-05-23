# Bot settings

The bot settings menu lets you change global settings that affect all trading pairs.

To change them, go to **Settings** &gt; **Bot Settings**.

![](../../.gitbook/assets/image%20%2832%29.png)

## Settings descriptions

Below you'll find detailed descriptions of all available parameters for bot settings. A few advanced settings are only available in the `config.json` file.

## Bot

### Watch Mode

{% tabs %}
{% tab title="Description" %}
When set to true, bitRage will process the configured pairs, but will not place actual buy or sell orders. Good for testing.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `WATCH_MODE`
{% endtab %}
{% endtabs %}

### Debug

{% tabs %}
{% tab title="Description" %}
Used to show debug messages in the bot, when set to true. Only use this if you really need to debug something.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `debug`
{% endtab %}
{% endtabs %}

## Operating

### Interval Ticker Update

{% tabs %}
{% tab title="Description" %}
Deprecated
{% endtab %}

{% tab title="Values" %}

{% endtab %}

{% tab title="Name" %}

{% endtab %}
{% endtabs %}

### Period Storage Ticker

{% tabs %}
{% tab title="Description" %}
Deprecated
{% endtab %}

{% tab title="Values" %}

{% endtab %}

{% tab title="Name" %}

{% endtab %}
{% endtabs %}

### Timeout Buy

{% tabs %}
{% tab title="Description" %}
This is an internal timeout that prevents the bot from buying again within the set amount of milliseconds after a buy order has been placed.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents time in milliseconds.

**Default value:** 60000
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `timeout_buy`
{% endtab %}
{% endtabs %}

### Timeout Sell

{% tabs %}
{% tab title="Description" %}
This is an internal timeout that prevents the bot from selling again within the set amount of milliseconds after a sell order has been placed.
{% endtab %}

{% tab title="Values" %}
**Values:** numerical – represents time in milliseconds.

**Default value:** 60000
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `timeout_sell`
{% endtab %}
{% endtabs %}


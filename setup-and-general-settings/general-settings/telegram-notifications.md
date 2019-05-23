# Telegram notifications

bitRage can send notifications on Telegram for every trade it places.

To set this up, go to **Settings** &gt; **Telegram**.

![](../../.gitbook/assets/image%20%2810%29.png)

## Steps to create a Telegram bot

Notifications work by first creating a personal bot on Telegram, bitRage then connects to this bot to push notifications to you.

This is how to create a bot:

1. Talk to [@botfather](https://telegram.me/botfather). Create a new bot with the command /newbot and choose a name and username for your bot. Save the bot token shown
2. Talk to [@myidbot](https://telegram.me/myidbot) to see your Chat ID, save it.
3. Enable Telegram notifications for bitRage, and enter the token and ID you've just gathered.
4. Start a chat with the username you've picked for your bot, and hit the start button. If you don't see a start button, write "/start" and click on it afterwards.

## Settings descriptions

Below you'll find detailed descriptions of all available parameters for Telegram notifications.

### Enabled

{% tabs %}
{% tab title="Description" %}
Enable this to have bitRage send trade notifications through Telegram.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `TELEGRAM_ENABLED`
{% endtab %}
{% endtabs %}

### Bot Nickname

{% tabs %}
{% tab title="Description" %}
Each trade notification starts with the nickname set here.

Use this to easily check from which bot instance the notifications have been sent.
{% endtab %}

{% tab title="Values" %}
**Values:** string

**Default value:** bitRage
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `TELEGRAM_NICK`
{% endtab %}
{% endtabs %}

### Token

{% tabs %}
{% tab title="Description" %}
The Telegram token for your bot.
{% endtab %}

{% tab title="Values" %}
**Values:** string

**Default value:** YOURTOKEN
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `TOKEN`
{% endtab %}
{% endtabs %}

### Chat ID

{% tabs %}
{% tab title="Description" %}
The Chat ID for your bot to send its messages to.

**Valid options:**

_**"12345"**_

A positive integer, to send messages directly to a telegram user. Use this method when you just want to receive notifications for your personal use.

To find your telegram id, send /start to @MyTelegramID\_bot and it will respond with your ID.

_**"-12345"**_

A negative integer, to send messages to a group chat.

The easiest way to obtain a groups id, is to open [https://web.telegram.org](https://web.telegram.org) login, and navigate to the group. Now pay attention to the URL, you should see something like [https://web.telegram.org/\#/im?p=g12345](https://web.telegram.org/#/im?p=g12345) - the number after the p=g part is the group id.

This must be listed in chat\_id with a - symbol in front, in this case "-12345"
{% endtab %}

{% tab title="Values" %}
**Values:** string or number

**Default value:** 123456789
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `chat_id`
{% endtab %}
{% endtabs %}

### Opportunity Found Notification

{% tabs %}
{% tab title="Description" %}
When enabled, sends a notification for every opportunity found.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** tbd
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `opp_found`
{% endtab %}
{% endtabs %}

### First Trade Notification

{% tabs %}
{% tab title="Description" %}
When enabled, sends a notification for every stage 1 order that gets placed.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** tbd
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `first_trade`
{% endtab %}
{% endtabs %}

### Second Trade Notification

{% tabs %}
{% tab title="Description" %}
When enabled, sends a notification for every stage 2 order that gets placed.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** tbd
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `second_trade`
{% endtab %}
{% endtabs %}

### Third Trade Notification

{% tabs %}
{% tab title="Description" %}
When enabled, sends a notification for every stage 3 order that gets placed.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** tbd
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `third_trade`
{% endtab %}
{% endtabs %}

### Sellback Trade Notification

{% tabs %}
{% tab title="Description" %}
When enabled, sends a notification for every sellback trade that gets placed.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false

**Default value:** tbd
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.json`: `sb_trade`
{% endtab %}
{% endtabs %}

### 


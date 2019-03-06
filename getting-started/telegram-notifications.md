# Telegram notifications

Gunbot can send notifications on Telegram for every trade it places. 

To set this up, go to **Settings** &gt; **Telegram**. 

![Available settings options for Telegram notifications.](../.gitbook/assets/image%20%281%29.png)



## Steps to create a Telegram bot

Notifications work by first creating a personal bot on Telegram, Gunbot then connects to this bot to push notifications to you.

This is how to create a bot:

1. Talk to [@botfather](https://telegram.me/botfather). Create a new bot with the command /newbot and choose a name and username for your bot. Save the bot token shown
2. Talk to [@myidbot](https://telegram.me/myidbot) to see your Chat ID, save it.
3. Enable Telegram notifications for Gunbot, and enter the token and ID you've just gathered.
4. Start a chat with the username you've picked for your bot, and hit the start button.



## Settings descriptions

Below you'll find detailed descriptions of all available parameters for Telegram notifications.

### Enabled

{% tabs %}
{% tab title="Description" %}
Enable this to have Gunbot send trade notifications through Telegram.
{% endtab %}

{% tab title="Values" %}
**Values:** true or false
{% endtab %}

{% tab title="Name" %}
Parameter name in `config.js`: `TELEGRAM_ENABLED`
{% endtab %}
{% endtabs %}


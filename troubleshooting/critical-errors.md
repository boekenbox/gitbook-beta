# Critical errors

When there is a problem that might need attention, bitRage usually shows an error notification in the GUI. Some errors are only visible in the console window running bitRage.

For troubleshooting purposes, recent logs are stored in the /logs folder. After bitRage is closed, logfiles can be read with a text editor like Notepad++.

This page describes common problems and their possible solutions.

{% hint style="success" %}
**Tips for troubleshooting**

Always completely close and restart bitRage before trying to resolve a critical issue. 

Reboot your computer when you are unsure if you've completely closed bitRage. 

When resolving an isse that might be related to API rate limiting, stop running bitRage for at least 30 minutes before trying to solve the problem.
{% endhint %}



## Errors when starting bitRage

The following errors are **critical** and will prevent trading, they indicate bitRage could not properly start or connect to an exchange.



### INVALID LICENSE FOR \(exchange\) Please contact your reseller!

**Reason:** master key is not registered

**Possible solutions:**

* Double check if your master key and secret are correct and do not start or end with a blank space.
* Verify that you are running the correct edition of bitRage.
* If the problem persists: contact your reseller.



### Unable to connect to exchange

**Reason:** Various, most often a problem with time sync or pair naming.

**Possible solutions:**

* Double check if your master key and secret are correct and do not start or end with a blank space.
* Check if your system clock is synced with an internet time server. [Tool for Windows](http://www.timesynctool.com/) / [Info for Linux](https://www.howtogeek.com/tips/how-to-sync-your-linux-server-time-with-network-time-servers-ntp)
* Make sure both a valid master key and key are present in your config.
* Make sure your pairs actually exist on the exchange and conform to bitRage pair syntax.
* Increase exchange delay, the exchange might have rate limited you. Stop bitRage and wait at least 30 minutes before retrying.
* Make sure all bitRage files were correctly unzipped.
* Make sure the IMAP listener is disabled \(when not using the TradingView add-on\).
* Try a wired internet connection.
* Restart your router and/or flush your DNS cache.



### Invalid response from license server

**Reason:** Usually a network issue

**Possible solutions:**

* Try a wired internet connection.
* Restart your router and/or flush your DNS cache.



### Error: bind EADDRINUSE null:5000

**Reason:** Other process is already using the specified port number

**Possible solutions:**

* Restart your computer.
* When other software requires using any of the ports needed for bitRage, change the ports bitRage uses in the config.json file.



### Can't access GUI anymore

**Reason:** Config error preventing core to properly load

**Solution:**

* Set `start` false in the GUI section of config.json, with a text editor like Notepad++. Save the file and you should be able to connect to the GUI again.



### SSL\_ERROR\_RX\_RECORD\_TOO\_LONG

**Reason:** https not enabled and the browser forces an https connection

**Possible solutions:**

* Enable `https` in the config.json file.
* Visit bitRage via http, instead of https.



### Invalid signature

**Reason:** API issue

**Possible solutions:**

* Double check your API secret.
* Make sure your API key is activated on CEX.
* Make sure you filled in your ClienID, passphrase or password in the exchange connection settings.



## Errors after successfully starting bitRage

The following orders can prevent trading when occurring very often. When any of these errors only occur intermittently, there is usually no issue that needs solving.



### Received broken open orders info: retrying again

**Reason:** Exchange did not send requested order data

**Possible solutions:**

* Ensure proper internet connectivity.
* Increase exchange delay.



### Fetching OHLC again

**Reason:** There is not enough trading volume to receive the number of requested candles

**Possible solutions:**

* Try a different setting for `PERIOD`
* Try other trading pairs with more volume.



### WARNING: BUY order from more than 30 days ago.

**Reason:** Bought price for asset is unknown

**Possible solutions:**

* Add `BOUGHT_PRICE` as an override for your pair. 



### TypeError: Cannot read x of undefined

**Reason:** Problem with one or your pairs

**Possible solutions:**

* Make sure that you have not accidentally removed one of your exchanges and still have pairs connected to it. 
* Check if all of the pairs in your setup actually exist on your exchange and conform to bitRage pair syntax \(BASE-QUOTE\).
* Wait until the exchange finishes possible maintenance.



### Poloniex: 422

**Reason:** Exceeding API rate limit

**Possible solution:**

* Increase the exchange delay for Poloniex.




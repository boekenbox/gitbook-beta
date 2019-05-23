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

### 


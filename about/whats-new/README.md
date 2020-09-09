---
description: >-
  Here's a quick overview of the most important changes introduced with Gunbot
  v20
---

# What's new?

Gunbot v20 introduces a completely new interface built around the TradingView charting library, with easier options to create and edit strategy settings. Also comes with a ton of other changes and stability improvements. 

## **Upgrading**

There are no breaking config changes for v20 In case you are upgrading from v18.x, replacing only the executable file \(gunthy-win.exe / gunthy-linux / gunthy-macos / gunthy-arm\) is all that's needed to upgrade - before trading, do check the strategy editor to see if your strategy doesn't miss any new parameters. The new GUI requires that password authentication is enabled.

In case you are upgrading from an older version, refer to the changelogs of previous versions for instructions, or start with a fresh installation.  
  
It could be that strategies made with a much older version don't include some new parameters. You would notice this when you see any blank fields in the strategy editor. Creating a new strategy with the GUI always guarantees that every single parameter is included.

{% page-ref page="../../setup-and-general-settings/installation/download.md" %}



## Changes in v20

Only the most important changes are listed.

### Core / GUI

* **Completely new GUI:** improved performance, easier to use, better charting, more stats 
* **Store more order history:** to improve profit/loss calculations and prevent unneeded "bought price" warnings, the complete order history is now locally saved over time 
* **PND close**: an alternative to ROE trailing to aim for bigger profits. PND attempts to wait until a move plays out before closing a margin position
* **TradingView alerts**: option to change strategy by alert, enable `TV_TRADING_LIMIT_CAP` for Bitmex
* **Alerts \(beta\):** build your own strategy in a visual way using built-in TradingView charts

### Market Maker

* **New strategy variants**: Grid, Support/Resistance, Fibonacci, x125 & Moto

### AutoConfig

* **Editor and stats in the GUI**: every single AutoConfig feature is now editable through the GUI, every config changed is visible on the AutoConfig dashboard
* **More filter types**: add pairs with linear regression filters, more [options ](../../how-to-work-with-gunbot/extras/autoconfig.md#generic-filters)to filter your own variables
* **Use your own logic:** most values in Autoconfig jobs can now optionally use [custom JavaScript expressions](../../how-to-work-with-gunbot/extras/autoconfig.md#calculated-config-values-and-custom-filters). Expressions have access to almost all internal bot data

### Bugfixes

* Numerous exchange specific trading execution fixes
* Fix closelong / closeshort alerts for Kraken Futures and Binance Futures
* Work around Kraken cloudflare issue in ccxt library
* Add support for all new pairs on Kraken \(on other exchange this happens automatically\)
* Prevent firing orders if MM bots receive sudden strange balance or ROE values
* Fix problem that prevented proper handover from DU to RT



{% page-ref page="../../setup-and-general-settings/installation/download.md" %}


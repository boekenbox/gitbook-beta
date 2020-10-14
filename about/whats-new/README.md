---
description: >-
  Here's a quick overview of the most important changes introduced with Gunbot
  v20
---

# What's new?

Gunbot v20 introduces a completely new interface built around the TradingView charting library, with easier options to create and edit strategy settings. Also comes with a ton of other changes and stability improvements. 

## **Upgrading**

There are no breaking config changes for v20. In case you are upgrading from v18.x, replacing only the executable file \(gunthy-win.exe / gunthy-linux / gunthy-macos / gunthy-arm\) is all that's needed to upgrade. 

**The new GUI requires that password authentication is enabled in** `config.js`**.**  
New strategy parameters are automatically merged into your strategies, as soon as you login to the browser interface.

In case you are upgrading from an older version, refer to the changelogs of previous versions for instructions, or start with a fresh installation.

{% page-ref page="../../setup-and-general-settings/installation/download.md" %}



## Changes in v20

Only the most important changes are listed.

### Core / GUI

* **Completely new GUI:** improved performance, easier to use, better charting, improved trading terminal, more stats, additional config wizard for novice users
* **Seamless config changes:** pair cycling is no longer interrupted when a config change happens. New settings take effect the next cycle
* **New supported partner exchanges:** Bitget and Nash
* **New strategy for spot trading**: [Support / Resistance](../../trading-strategy-options/regular-strategies-spot-trading/support-resistance.md)
* **PND close**: an alternative to ROE trailing to aim for bigger profits in margin strategies. PND attempts to wait until a move plays out before closing position
* **Alternate ROE trailing method  for margin strats:** with `ROE_SCALPER` the trailing range is an absolute ROE value
* **Liquidity maker for spot trading:** provide [liquidity ](../../trading-strategy-options/misc-settings.md#liquidity-maker)and profit from bid/ask spread
* **Store more order history:** to improve profit/loss calculations and prevent unneeded "bought price" warnings, the complete order history is now locally saved over time 
* **TradingView alerts**: option to change strategy by alert, enable `TV_TRADING_LIMIT_CAP` for Bitmex
* **Alerts \(beta\):** build your own strategy in a visual way using built-in TradingView charts

### Market Maker

* **New strategy variants**: Grid, Support/Resistance, Fibonacci, Pullback, One Scalper, x125 & Moto

### AutoConfig

* **Editor and stats in the GUI**: every single AutoConfig feature is now editable through the GUI, every config change is visible on the AutoConfig dashboard
* **More filter types**: add pairs with linear regression filters, more [options ](../../how-to-work-with-gunbot/extras/autoconfig.md#generic-filters)to filter your own variables
* **Use your own logic:** most values in Autoconfig jobs can now optionally use [custom JavaScript expressions](../../how-to-work-with-gunbot/extras/autoconfig.md#calculated-config-values-and-custom-filters). Expressions have access to almost all internal bot data
* **Silent mode**: disable console logs for AutoConfig

### Bugfixes

* Numerous exchange specific trading execution fixes
* Fix closelong / closeshort alerts for Kraken Futures and Binance Futures
* Work around Kraken cloudflare issue in ccxt library
* Add support for all new pairs on Kraken \(on other exchange this happens automatically\)
* Prevent firing orders if MM bots receive sudden strange balance or ROE values
* Fix problem that prevented proper handover from DU to RT



{% page-ref page="../../setup-and-general-settings/installation/download.md" %}


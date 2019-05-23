# Logs

bitRage logs contain most of the information it works with. This article provides an overview of the different sections in these logs, and explains how to read them.

Log files per trading pair are automatically saved in the /logs folder and automatically rotated to zipped backups after reaching a filesize of 25MB. Up to three backup logfiles are kept per trading pair.

## The "grid"

The console log output of bitRage is condensed into one grid showing the relevant data for the "pair" that is being processed. 

![](../.gitbook/assets/image%20%2816%29.png)

### **Prices, balances and volume**

On the left side of the grid information is shown for the prices, balances and volume checks that bitRage does every round. 

Important to know about this overview is that when a cells data is marked red, it's not profitable enough to proceed. It can happen that you'll see a triple seems profitable, but one of the volume checks is marked red. This means that there is not sufficient trading volume to proceed with executing trades.

Data in the `bitRage` rows apply for regular trades. Data in the `Revert` rows apply for reversed trades for the same pairs.

The `Cross Rate` shown is an artificial price used to compare the profitability of two different markets, for example BTC-MANA and BTC-ETH.

The `Initial amount` is the amount of base currency that bitrage will attempt to invest for an opportunity. `The Final Amount` and `Final Amount RT` stats are the expected outcomes of an opportunity.



### State and profitability checks

Below the `State` field you can see the current stage a pair is in. When no stage is shown, it means that it did not yet start trading on an opportunity, or is waiting for the exchange to provide data for a stage1 order.

The various profitability checks show the expected profitability for an opportunity, when executed in `crazybitch` mode. If a pair is profitable in safe mode can be seen next to the `SAFE profitable` field.

## HUD

When you run your logs in HUD mode, instead of the usual grid output it will show a continuously updated summary of the status of your set trading pairs.

![](../.gitbook/assets/image%20%2824%29.png)

### \*\*\*\*


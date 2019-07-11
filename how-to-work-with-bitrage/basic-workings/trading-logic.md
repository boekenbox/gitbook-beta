# Trading logic

## What is bitRage about?

The basic principle of bitRage is to profit from a price imbalance of a quote currency between two base currencies.

**Basic example:**

* If you can buy 100 ADA for 1 BTC,
* then sell 100 ADA for ETH, then sell ETH for BTC,
* and the result of the third trade, after trading fees, is more than 1 BTC, this is is an opportunity bitRage could exploit.

Note that bitRage often won't fire all three trades immediately. In safe mode it will actually play with the order book to make the opportunity happen.

In safe mode it can happen that before stage2 is executed, it's profitable to sell back the quote bought in the first trade. In that case bitRage chooses to place a sellback order instead of proceeding with arbitraging, this mechanism prevents bags.



## Process for a direct arbitrage opportunity

In the so called "crazybitch" mode using the websocket connection, bitRage will try to execute an arbitrage opportunity as soon as possible, using market orders if the exchange allows for that.

The basic process for executing such an opportunity is:  


1. Check profitability using tickers.
2. In case it looks profitable, profitability is checked in detail using the order books for all involved trading pairs.
3. When the order books confirm profitability, trades are fired. The normal process is that they are fired after another and keep retrying until done. Using the `PARALLEL_TRADES` option, trades can be fired simultaneously. 

In case a trade fails in step 3, for example because the exchange is slow in providing up to date balances, bitRage will attempt to retry trades over and over until it finishes arbitrage.



## Changing settings on a running trading pair

todo

## Manual trading

todo


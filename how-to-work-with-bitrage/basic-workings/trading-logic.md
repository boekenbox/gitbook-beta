# Trading logic

## What is bitRage about?

The basic principle of bitRage is to profit from a price imbalance of a quote currency between two base currencies.

**Basic example:**

* If you can buy 100 ADA for 1 BTC,
* then sell 100 ADA for ETH, then sell ETH for BTC,
* and the result of the third trade, after trading fees, is more than 1 BTC, this is is an opportunity bitRage could exploit.

Note that bitRage often won't fire all three trades immediately. In safe mode it will actually play with the order book to make the opportunity happen.

In safe mode it can happen that before stage2 is executed, it's profitable to sell back the quote bought in the first trade. In that case bitRage chooses to place a sellback order instead of proceeding with arbitraging, this mechanism prevents bags.

## Changing settings on a running trading pair

todo

## Manual trading

todo


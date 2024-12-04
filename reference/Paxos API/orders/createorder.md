---
title: Create Order
excerpt: >-
  For limit orders, create an order for buying or selling an asset:


  - To buy, set `side = BUY` and set `base_amount` to the crypto amount you want
  to buy.

  - To sell, set `side = SELL` and set `base_amount` to the crypto amount you
  want to sell.


  For market orders, create an order for buying or selling an asset:


  - To buy, set `side = BUY` and set `quote_amount` to the dollar amount you
  want to spend.

  - To sell, set `side = SELL` and set `base_amount` to the crypto amount you
  want to sell.


  There are five types of orders:


  - Limit Orders: Buy or sell at a specified price or better. Execution not
  guaranteed. Taker orders will be rejected if price deviates 15% from midpoint.

  - Post-Only Limit Orders: have the same properties as Limit Orders, but get
  rejected if they cross the orderbook.

  - Market Orders: Operate as Immediate or Cancel (IOC) orders. Price is
  variable, executes at best available price at time of order.

  - Stop Market Orders: Will convert to a market sell order with the specified
  quantity when the stop price is hit. The stop price does not guarantee that it
  will be executed at that price. Market conditions (price) might change between
  the order being triggered and order being executed. Currently only sell stop
  loss orders are supported.

  - Stop Limit Orders: have a Stop Price which when hit, will convert to a limit
  sell order that will be executed at a specified price (or better)


  Maximum notional order size by type:


  Order Type | Market  | Maximum Notional Value (USD)

  ---------- | ------- | ----------------------------

  Market     | all     | 500,000

  Limit      | BTCUSD  | 1,500,000

  Limit      | ETHUSD  | 1,500,000

  Limit      | other   | 1,000,000
api:
  file: paxos.json
  operationId: CreateOrder
hidden: false
---
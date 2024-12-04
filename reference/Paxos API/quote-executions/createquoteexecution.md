---
title: Create Quote Execution
excerpt: >-
  Execute on a quote for buying or selling an asset.


  The side, market, and guaranteed price of the execution are specified by the
  quote

  with ID `quote_id`.


  The amount to buy or sell must be specified in either fiat or crypto by
  setting

  exactly one of:
   - `base_amount` to specify the amount of crypto to buy or sell.
   - `quote_amount` to specify the amount of fiat to spend or acquire.

  An otherwise-valid request to create a quote execution may fail with the
  following

  types of errors:
   - [Expired](https://developer.paxos.com/docs/v2/problems/expired) if the quote
     with ID `quote_id` has expired.
   - [Insufficient Funds](https://developer.paxos.com/docs/v2/problems/insufficient-funds)
     if the profile with ID `profile_id` has insufficient available balance to
     fund the execution.
   - [Rejected](https://developer.paxos.com/docs/v2/problems/rejected) if extreme
     market conditions (e.g. a very large price swing) have invalidated the quote.
   - [Already Exists](https://developer.paxos.com/docs/v2/problems/already-exists)
     if a Quote Execution with the same `ref_id` has already been created.
api:
  file: paxos.json
  operationId: CreateQuoteExecution
hidden: false
---
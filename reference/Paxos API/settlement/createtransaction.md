---
title: Create Transaction
excerpt: >-
  Creates a new bilateral Settlement Transaction with one or more legs. The
  customer must own the

  `source_profile_id` specified in the transaction.


  A successful response indicates the transaction has been accepted and will be
  in an initial `status` of `"PENDING"`

  for settlement, the transaction is only eligible for settlement once the
  `status` is `"AFFIRMED"` by the

  `target_profile_id` and the current time is between the provided
  `settlement_window_start` and `settlement_window_end`.


  Settlement will only be enacted once both `source_profile_id` and
  `target_profile_id` have sufficient balances to

  fulfill all legs specified as settlement is **atomic**.
api:
  file: paxos.json
  operationId: CreateTransaction
hidden: false
---
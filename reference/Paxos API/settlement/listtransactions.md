---
title: List Transactions
excerpt: >-
  This endpoint enables you to fetch a list of Settlement Transactions that you
  have created (own the `source_profile_id`) or have been alleged against you
  (own the `target_profile_id`).

  You can use query parameters to filter the results returned by `statuses`,
  `source_profile_id` and `target_profile_id`.


  Note that this endpoint supports pagination and returns a cursor token for
  fetching next pages.
api:
  file: paxos.json
  operationId: ListTransactions
hidden: false
---
---
title: List Transfers
excerpt: |-
  List all transfers, optionally filtering and paging the results.

  By default, transfers are returned in reverse chronological (descending)
  order by creation time.

  The recommended polling workflow is to query the results in ascending
  order (by setting `order_by` to `CREATED_AT`), keeping track of the
  `created_at` timestamp of the most recent transfer in the paged results.
  Once transfers are discovered, the caller should store the returned `ID`
  and query GetTransfer to retrieve status updates.
api:
  file: paxos.json
  operationId: ListTransfers
hidden: false
---
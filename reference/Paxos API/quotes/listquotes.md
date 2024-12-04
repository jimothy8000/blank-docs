---
title: List Quotes
excerpt: |-
  List quotes for buying or selling assets. By default, the list will
  include the latest available quotes for both buying and selling all supported
  assets.

  Each quote is valid until `expires_at`, and can be executed on by
  calling [Create Quote Execution](#operation/CreateQuoteExecution).

  Multiple calls to list quotes in quick succession may return the same quote
  values. Paxos currently issues new quotes at most once per second.
api:
  file: paxos.json
  operationId: ListQuotes
hidden: false
---
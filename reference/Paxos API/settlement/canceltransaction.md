---
title: Cancel Transaction
excerpt: >-
  Cancels the Settlement Transaction, this action can only be done by the
  customer owning the source profile (`source_profile_id`).

  The transaction must be in a `"PENDING"` status for this to take effect, you
  cannot cancel a transaction which

  is `"AFFIRMED"`.
api:
  file: paxos.json
  operationId: CancelTransaction
hidden: false
---
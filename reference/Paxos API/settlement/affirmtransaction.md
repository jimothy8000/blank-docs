---
title: Affirm Transaction
excerpt: >-
  Affirms the Settlement Transaction for settlement, the transaction is now
  eligible for settlement once the current time is

  between the provided `settlement_window_start` and `settlement_window_end`.
  This action can only be done by the

  customer owning the target profile (`target_profile_id`).

  The transaction must be in a `"PENDING"` status for this to take effect.
api:
  file: paxos.json
  operationId: AffirmTransaction
hidden: false
---
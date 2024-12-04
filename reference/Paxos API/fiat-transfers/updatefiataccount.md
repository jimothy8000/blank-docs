---
title: Update Fiat Account
excerpt: >-
  Change an existing value or add a new value on one or more fields for the
  given Fiat Account and return the modified Fiat Account in `PENDING` status.

  Update fields in **either** `fiat_account_owner.person_details` or
  `fiat_account_owner.institution_details`.

  Attempts to convert the `fiat_account_owner` type results in an error.

  Empty strings or null values are ignored.


  Upon successful response, Paxos initiates an automated review of the requested
  changes and then either sets the status to `APPROVED` or `REJECTED`.

  Occasionally, a manual review may be required.

  Use [Get Fiat Account](#operation/GetFiatAccount) to check for status changes.
api:
  file: paxos.json
  operationId: UpdateFiatAccount
hidden: false
---
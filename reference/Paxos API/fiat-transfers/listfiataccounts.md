---
title: List Fiat Accounts
excerpt: >-
  List all Fiat Accounts, optionally filtering and paging the results.

  The response includes an abbreviated `FiatAccount` object:


  - Beneficiary name and address details are excluded.

  - Only the last four (**4**) digits of the account number are included.


  Use [Get Fiat Account](#operation/GetFiatAccount) to retrieve the complete
  `FiatAccount` object.


  The paginated results default to the maximum limit of 1,000 Fiat Accounts,
  unless otherwise specified with the `limit` parameter.

  Every paginated response contains a `next_page` field until the last page is
  reached.

  Pass the `next_page` value into the `page_cursor` field of the next request to
  retrieve the next page of results.
api:
  file: paxos.json
  operationId: ListFiatAccounts
hidden: false
---
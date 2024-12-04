---
title: List Tax Lots
excerpt: >-
  List Tax Lots, optionally filtering and paging the results.

  The paginated results default to 100 items, unless otherwise specified with
  the `limit` parameter.

  Every paginated response contains a `next_page_cursor` until the last page is
  reached.

  Pass the `next_page` value into the `page_cursor` field of the next request to
  retrieve the next page of results.
api:
  file: paxos.json
  operationId: ListTaxLots
hidden: false
---
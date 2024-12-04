---
title: List Profiles
excerpt: >-
  Return the associated Profiles for the current Account.

  The paginated results default to the maximum limit of 1,000 Profiles, unless
  otherwise specified with the `limit` parameter.

  Every paginated response contains a `next_page` field until the last page is
  reached.

  Pass the `next_page` value into the `page_cursor` field of the next request to
  retrieve the next page of results.
api:
  file: paxos.json
  operationId: ListProfiles
hidden: false
---
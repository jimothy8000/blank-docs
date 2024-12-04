---
title: List Historical Prices
excerpt: >-
  Retrieves a set of average prices at a certain increment of time for the
  requested market.

  This endpoint is suitable for retrieving historical average price trends where
  price precision, execution, and

  other detailed information is not required.

  To control the count, use either  `increment` or `max_data_points`.

  List Historical Prices returns an error when an unexpected value is given, or
  when `increment` and
   `max_data_points` are both given or omitted.

  When `range.begin` is omitted, the first data point shows the mid price, the
  average of the order book best bid
   and ask price, or the earliest available date. It is possible to set `range.begin` to a future date without error.

  When `range.end` is omitted, the last data point will display current mid
  price (average of order book best bid
   and best ask) at the request timestamp. It is possible to set `range.end` to a future date without error.

  When `pagination.limit` is omitted, the pagination limit will default to
  return the first 100 items.

  If the pagination limit is set, the API will return up to the limit in one
  response. The pagination limit max is 1,000.


  Time-series items are returned in chronological (ascending) order. All
  timestamps are in UTC.
api:
  file: paxos.json
  operationId: ListHistoricalPrices
hidden: false
---
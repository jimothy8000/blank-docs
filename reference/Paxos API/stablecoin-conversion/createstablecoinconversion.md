---
title: Create Stablecoin Conversion
excerpt: |-
  Create a Conversion request to exchange assets 1:1.

  A request to create a conversion can fail with one of the following
  types of errors:
   - [Insufficient Funds](https://developer.paxos.com/docs/v2/problems/insufficient-funds)
     if the Profile (`profile_id`) has insufficient available balance to
     fund the execution.
   - [Already Exists](https://developer.paxos.com/docs/v2/problems/already-exists)
     if a conversion with the same external ID (`ref_id`) has already been created.
api:
  file: paxos.json
  operationId: CreateStablecoinConversion
hidden: false
---
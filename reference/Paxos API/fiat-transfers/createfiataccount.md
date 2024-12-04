---
title: Create Fiat Account
excerpt: >-
  Create an account to initiate a fiat withdrawal.


  For U.S. wires, set `fiat_network_instructions` > `wire` > `routing_details` >
  `routing_number_type` to `ABA`. For international (SWIFT) wires, set
  `fiat_network_instructions` > `wire` > `routing_details` >
  `routing_number_type` to `SWIFT`.


  For CBIT, set `fiat_network_instructions` > `cbit` > `wallet_address`, and do
  not specify `routing_number_type`. For CBIT, the `wallet_address` on
  `fiat_network_instructions` is not a crypto wallet, it is a Customers Bank
  account wallet address.
api:
  file: paxos.json
  operationId: CreateFiatAccount
hidden: false
---
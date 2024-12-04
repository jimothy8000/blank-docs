---
title: Create Crypto Withdrawal Fee
excerpt: >-
  Get a guaranteed fee for the given currency, valid for a period of time.

  Specify exactly one of `amount` or `total`, otherwise an error is returned.


  The [Create Crypto Withdrawal](#operation/CreateCryptoWithdrawal) request that
  uses the guaranteed fee endpoint

  must specify an `amount` less than or equal to the guaranteed fee `amount`,
  otherwise the withdrawal is rejected.
api:
  file: paxos.json
  operationId: CreateCryptoWithdrawalFee
hidden: false
---
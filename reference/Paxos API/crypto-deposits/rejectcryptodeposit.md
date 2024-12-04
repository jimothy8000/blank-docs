---
title: Reject Crypto Deposit
excerpt: >-
  Reject a crypto deposit which is waiting for required travel rule information
  about the originator address.

  If the rejected deposit has any status other than `NEEDS_INFO`, the request
  will return an error.

  Only the creator of the crypto deposit can reject it.
api:
  file: paxos.json
  operationId: RejectCryptoDeposit
hidden: false
---
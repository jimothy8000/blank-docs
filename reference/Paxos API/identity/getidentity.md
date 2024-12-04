---
title: Get Identity
excerpt: >-
  Get an identity by ID. By default, the identity details (person_details or
  institution_details) will not be returned.

  Set `?include_details=true` to receive them in the response. For institution
  type identities,

  members will not be returned in the default response. Set
  `?include_institution_members=true` to get the members.


  An identity is allowed to transact on the Paxos platform when `summary_status`
  is `"APPROVED"`.
api:
  file: paxos.json
  operationId: GetIdentity
hidden: false
---
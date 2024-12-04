---
title: Sandbox Set Identity Status
excerpt: >-
  Set the various statuses for the given Identity. To enable the Person Identity
  to transact,

  set both `id_verification_status` and `sanctions_verification_status` to
  `"APPROVED"`.

  To enable the Institution to transact, set both
  `sanctions_verification_status` to `"APPROVED"`.

  This endpoint also allows you to set the statuses for
  `document_verification_status` and

  `additional_screening_status`
api:
  file: paxos.json
  operationId: SandboxSetIdentityStatus
hidden: false
---
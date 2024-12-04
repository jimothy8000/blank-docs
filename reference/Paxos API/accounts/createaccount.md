---
title: Create Account
excerpt: >-
  Create an account for a given identity, via the `identity_id` field.

  This identity is the primary owner of the account for all tax-related
  purposes.


  To track user balances using Paxos [Profiles](#tag/Profiles), use
  `create_profile=true` when creating the account.

  Once an account has been created, it is not possible to associate it with a
  [Profile](#tag/Profiles).


  ### Account Members


  In addition to the primary owner, other identities may be associated with the
  account, by using `members`.

  The identity on the account is treated as a BENEFICIAL_OWNER.


  To add a financial advisor to an account, add a member with the
  FINANCIAL_ADVISOR role.


  #### Example

  This example request creates a joint account for John and Jane Doe. John has
  identity_id=82c338f4-3cb7-4d9b-be2a-4b077c82ee3a,

  and Jane has identity_id=0f5d8475-33f3-4ebd-88a0-66dedc2581c1. John is the
  primary owner of the account for tax-purposes, but Jane

  is a full beneficial owner.


  Additionally, this account has an associated financial advisor with
  identity_id=0d26f878-298e-4d47-81be-cdf4e982a3d3.


  <!--indentation does not work in swagger code blocks-->

  <pre>

  <code>

  {

  &nbsp;&nbsp;"account": {

  &nbsp;&nbsp;&nbsp;&nbsp;"identity_id": "82c338f4-3cb7-4d9b-be2a-4b077c82ee3a",

  &nbsp;&nbsp;&nbsp;&nbsp;"members": [{

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "0f5d8475-33f3-4ebd-88a0-66dedc2581c1",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["BENEFICIAL_OWNER"]

  &nbsp;&nbsp;&nbsp;&nbsp;}, {

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "0d26f878-298e-4d47-81be-cdf4e982a3d3",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["FINANCIAL_ADVISOR"]

  &nbsp;&nbsp;&nbsp;&nbsp;}]

  &nbsp;&nbsp;}

  }

  </code>

  </pre>


  ### Fields


  Any fields not listed are forbidden in this request.


  Field | Notes

  ---|---

  identity_id | Required

  description | Optional

  metadata | Optional

  ref_id | Optional

  members | Optional
api:
  file: paxos.json
  operationId: CreateAccount
hidden: false
---
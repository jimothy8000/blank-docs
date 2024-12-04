---
title: Update Account
excerpt: >-
  This enables you to update an existing account with new information. Please
  refer to the following

  table for fields that can be updated via this endpoint.


  Field | Notes

  ---|---

  account.id | Required

  account.description | Optional

  account.ref_id | Optional

  account.metadata | Optional. This will overwrite any existing metadata added
  to the account.

  account.members | Optional. The only roles that can be added/removed are
  `FINANCIAL_ADVISOR` or `AUTHORIZED_USER.` You must always specify the full
  members object as we do not currently support differential member updates.

  set_user_disabled | Optional. Setting this to `true` will disable the account,
  limiting its ability to be used within the Paxos platform.


  #### Example Requests

  #### Disabling an account


  <!--indentation does not work in swagger code blocks-->

  <pre>

  <code>

  {

  &nbsp;&nbsp;"set_user_disabled": true,

  &nbsp;&nbsp;"account": {

  &nbsp;&nbsp;&nbsp;&nbsp;"id": "82c338f4-3cb7-4d9b-be2a-4b077c82ee3a",

  &nbsp;&nbsp;&nbsp;&nbsp;"description": "Account Description",

  &nbsp;&nbsp;&nbsp;&nbsp;"ref_id": "82c338f4-3cb7",

  &nbsp;&nbsp;}

  }

  </code>

  </pre>


  ### Adding an account member

  To retain the existing account members and add a new account member, the
  `members` field must contain the existing account members and the

  new member. The below example adds an `AUTHORIZED_USER` to the account.


  In order to add account members while leaving existing account members
  unaffected, clients

  should use the [Add Account Members](#operation/AddAccountMembers) API.


  <!--indentation does not work in swagger code blocks-->

  <pre>

  <code>

  {

  &nbsp;&nbsp;"account": {

  &nbsp;&nbsp;&nbsp;&nbsp;"id": "82c338f4-3cb7-4d9b-be2a-4b077c82ee3a",

  &nbsp;&nbsp;&nbsp;&nbsp;"members": [{

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "0f5d8475-33f3-4ebd-88a0-66dedc2581c1",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["BENEFICIAL_OWNER"]

  &nbsp;&nbsp;&nbsp;&nbsp;}, {

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "0d26f878-298e-4d47-81be-cdf4e982a3d3",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["FINANCIAL_ADVISOR"]

  &nbsp;&nbsp;&nbsp;&nbsp;}, {

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "012k23eb-298e-4d47-81be-cdf4e982a3d3",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["AUTHORIZED_USER"]

  &nbsp;&nbsp;&nbsp;&nbsp;}]

  &nbsp;&nbsp;}

  }

  </code>

  </pre>


  ### Removing an account member

  To remove an existing account member and retain other needed members, the
  `members` field must contain

  the existing account members without the account member you'd like to remove.
  The below example removes an `AUTHORIZED_USER` from the account.


  Note, this API requires the `members` array to have at least one element. In
  order to delete all members

  from an account, clients should use the [Delete Account
  Member](#operation/DeleteAccountMember) API.


  <!--indentation does not work in swagger code blocks-->

  <pre>

  <code>

  {

  &nbsp;&nbsp;"account": {

  &nbsp;&nbsp;&nbsp;&nbsp;"id": "82c338f4-3cb7-4d9b-be2a-4b077c82ee3a",

  &nbsp;&nbsp;&nbsp;&nbsp;"members": [{

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "0f5d8475-33f3-4ebd-88a0-66dedc2581c1",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["BENEFICIAL_OWNER"]

  &nbsp;&nbsp;&nbsp;&nbsp;}]

  &nbsp;&nbsp;}

  }

  </code>

  </pre>


  ### Updating an account members' roles

  To update an account members' roles, the `members` field must contain all the
  existing members with their roles along

  with the additional role that you'd like to add or remove. The below example
  adds the `FINANCIAL_ADVISOR` role to an member that is already a
  `BENEFICIAL_OWNER`.


  <!--indentation does not work in swagger code blocks-->

  <pre>

  <code>

  {

  &nbsp;&nbsp;"account": {

  &nbsp;&nbsp;&nbsp;&nbsp;"id": "82c338f4-3cb7-4d9b-be2a-4b077c82ee3a",

  &nbsp;&nbsp;&nbsp;&nbsp;"members": [{

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "0f5d8475-33f3-4ebd-88a0-66dedc2581c1",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["BENEFICIAL_OWNER",
  "FINANCIAL_ADVISOR"]

  &nbsp;&nbsp;&nbsp;&nbsp;}]

  &nbsp;&nbsp;}

  }

  </code>

  </pre>
api:
  file: paxos.json
  operationId: UpdateAccount
hidden: false
---
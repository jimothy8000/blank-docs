---
title: List Tax Forms
excerpt: >-
  Used for bulk file transfer use cases.

  List tax forms for given account ids and tax year. The most recent revision
  number will be returned (revisions increment up; highest value revision for a
  specific account, tax year, and form type pairing is the most recent).

  Tax Form URL links will expire after 60 seconds.

  Please call ListTaxFormRevisions endpoint for all versions of a single
  accounts tax forms.
api:
  file: paxos.json
  operationId: ListTaxForms
hidden: false
---
---
title: Update Identity
excerpt: >-
  This enables you to update an existing identity with new information. Please
  note that:

  - Updating any field other than `set_user_disabled`, `metadata`, `ref_id`, or
  `is_merchant` will transition the identity to a PENDING status.

  This will restrict the identity until it has been re-verified.

  - Setting `set_user_disabled` to `true` will disable the identity, limiting
  its ability to be used within

  the Paxos platform.

  - Setting `is_merchant` to `true` will indicate that this identity is a
  merchant.

  - Details of the identity can be updated by providing `person_details` or
  `institution_details` depending upon the type.

  - You can add, update or remove tax_details by providing the `tax_details`
  list. The tax_details will be updated to exactly

  comprise the given list


  Note: Identity conversion from person to institution type or vice-versa is not
  permitted.
api:
  file: paxos.json
  operationId: UpdateIdentity
hidden: false
---
---
title: Create Identity
excerpt: >-
  This enables you to create a new identity within the Paxos platform. Depending
  upon the fields provided, the

  identity will either be person or an institution.


  - [create person identity](#create-person-identity)

  - [create institution identity](#create-institution-identity)


  A successful response indicates that the identity has been created. This does
  not mean that

  it has already been processed. You can use the unique ID returned within the
  response to check

  the approval status of the identity.


  ### Create Person Identity

  The Person identity type is used to represent individuals on the platform.
  Attributes of the Person identity type are recorded in the *person_details*
  field.


  Note that fields not listed below are forbidden in this request.


  Field | Notes

  ---|---

  person_details | Required

  metadata | Optional

  tax_details | Optional

  ref_id | Optional


  For US based identities, if the `tax_details` attribute is empty, it will be
  backfilled with the `cip_id` and `cip_id_country` fields from the
  `person_details` attribute.

  For international identities, the `tax_details` attribute must be present.


  Currently both `JUMIO` or `PASSTHROUGH` are supported for verification, but
  only `JUMIO` is enabled by default.


  - [create person identity with jumio
  verification](#automatic-id-verification-with-jumio)

  - [create person identity with passthrough
  verification](#automatic-id-verification-with-passthrough)


  #### Automatic ID Verification with Jumio

  To use Jumio, you must submit the fields listed below as part of the
  `person_details` attribute in your request.


  Field | Notes

  ---|---

  person_details.verifier_type | Required. Must be `JUMIO`

  person_details.verifier_id | Required

  person_details.address | Required


  Please note that when using this method:

  - You must ensure that the identity has already been validated by Jumio before
  submitting the identity to Paxos.

  - You must have previously [set the API credentials for Jumio
  access](#operation/SetVerifierCredentials).


  Paxos will compare the provided information with the information returned from
  the Jumio API.


  In the event that there is a conflict between the submitted data and the data
  returned from the identity provider,

  the information from the identity provider will be preferred.


  ##### Example Request

  <!--indentation does not work in swagger code blocks-->

  <pre>

  <code>

  {

  &nbsp;&nbsp;"person_details": {

  &nbsp;&nbsp;&nbsp;&nbsp;"verifier_id": "b7b77d82-e6a7-4ae9-9904-36231aedf985",

  &nbsp;&nbsp;&nbsp;&nbsp;"verifier_type": "JUMIO",

  &nbsp;&nbsp;&nbsp;&nbsp;"first_name": "John",

  &nbsp;&nbsp;&nbsp;&nbsp;"last_name": "Doe",

  &nbsp;&nbsp;&nbsp;&nbsp;"date_of_birth": "1980-01-01",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id": "111-11-1111",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id_type": "SSN",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id_country": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;"nationality": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;"profession": "Engineer",

  &nbsp;&nbsp;&nbsp;&nbsp;"country_of_birth": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;"address": {

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"country": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"address1": "1 Example St",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"city": "New York",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"province": "NY",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"zip_code": "10001"

  &nbsp;&nbsp;&nbsp;&nbsp;},

  &nbsp;&nbsp;&nbsp;&nbsp;"ref_id": "33ece656-eef1-43b5-a851-b6b9099089a5"

  &nbsp;&nbsp;}

  }

  </code>

  </pre>


  #### Automatic ID Verification with Passthrough

  To use Passthrough, Paxos Compliance must first confirm your eligibility.


  Once confirmed, you can submit the fields listed below as part of the the
  `person_details` attribute in your request.


  | Field                                          |
  Notes                                                                                                    
  |

  |------------------------------------------------|-----------------------------------------------------------------------------------------------------------|

  | person_details.verifier_type                   | Required. Must be
  `PASSTHROUGH`                                                                          
  |

  | person_details.passthrough_verifier_type       | Required. Specifies the ID
  Verification provider you originally used                                     
  |

  | person_details.passthrough_verified_at         |
  Required                                                                                                 
  |

  | person_details.passthrough_verification_id     | Unique identifier for the
  underlying individual's ID verification
  record.                                 |

  | person_details.passthrough_verification_status | Status of the ID
  verification indicating whether the identity was approved or
  denied.                     |

  | person_details.passthrough_verification_fields | List of verification fields
  used by the external verifier to validate the individual's identity.         
  |

  | person_details.address                         |
  Required                                                                                                 
  |


  Note that the following field is forbidden in the request:

  `person_details.verifier_id`


  ##### Example Request

  <!--indentation does not work in swagger code blocks-->

  <pre>

  <code>

  {

  &nbsp;&nbsp;"person_details": {

  &nbsp;&nbsp;&nbsp;&nbsp;"verifier_type": "PASSTHROUGH",

  &nbsp;&nbsp;&nbsp;&nbsp;"passthrough_verifier_type": "JUMIO",

  &nbsp;&nbsp;&nbsp;&nbsp;"passthrough_verified_at": "2021-06-16T09:28:14Z",

  &nbsp;&nbsp;&nbsp;&nbsp;"passthrough_verification_id":
  "775300ef-4edb-47b9-8ec4-f45fe3cbf41f",

  &nbsp;&nbsp;&nbsp;&nbsp;"passthrough_verification_status": "APPROVED",

  &nbsp;&nbsp;&nbsp;&nbsp;"passthrough_verification_fields": ["FULL_LEGAL_NAME",
  "DATE_OF_BIRTH"]

  &nbsp;&nbsp;&nbsp;&nbsp;"first_name": "John",

  &nbsp;&nbsp;&nbsp;&nbsp;"last_name": "Doe",

  &nbsp;&nbsp;&nbsp;&nbsp;"date_of_birth": "1980-01-01",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id_type": "SSN",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id": "111-11-1111",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id_country": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;"nationality": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;"profession": "Engineer",

  &nbsp;&nbsp;&nbsp;&nbsp;"country_of_birth": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;"address": {

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"country": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"address1": "1 Example St",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"city": "New York",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"province": "NY",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"zip_code": "10001"

  &nbsp;&nbsp;&nbsp;&nbsp;},

  &nbsp;&nbsp;&nbsp;&nbsp;"ref_id": "33ece656-eef1-43b5-a851-b6b9099089a5"

  &nbsp;&nbsp;}

  }

  </code>

  </pre>


  ### Create Institution Identity

  Institution identities are used to represent all non-person entities.

  Details for institution identity type are recorded in `institution_details`.
  An institution identity also has `institution_members` associated with it.
  This defines persons or other entities that have some relationship to the
  institution.


  We support the following types and sub-types of institutions. Note that all
  institution types listed do share some common validations that can also be
  found below.


  #### Supported Institution Types


  institution_type | Supported institution_member roles | Notes

  ---| ---| ---

  `TRUST` | `BENEFICIAL_OWNER`<br>`BENEFICIARY`<br>`GRANTOR`<br>`TRUSTEE` | [See
  Trusts](#trust-institutions-requirement)

  `CORPORATION`<br>`LLC`<br>`PARTNERSHIP` |
  `ACCOUNT_OPENER`<br>`AUTHORIZED_USER`<br>`BENEFICIAL_OWNER`<br>`MANAGEMENT_CONTROL_PERSON`
  | [See other Institutions](#institutions-requirement)


  #### Industry Type to Institution Subtypes Mapping

  institution_sub_type | industry

  ---| ---

  `ACCOMMODATION_FOOD_SERVICES` |   Food or Beverage Services

  `ADMINISTRATIVE_SUPPORT_WASTE_MANAGEMENT_REMEDIATION_SERVICES` | 
  Administrative and Support Services

  `ADULT_ENTERTAINMENT` | Adult Entertainment / Pornography

  `AGRICULTURE_FORESTRY_FISHING_HUNTING` | Agriculture

  `ARTS_ENTERTAINMENT_RECREATION` | Arts, Entertainment, and Recreation

  `AUCTIONS` | Auction Houses / Art Galleries

  `AUTOMOBILES` | Automobiles / Automotives

  `BLOCKCHAIN` | Blockchain Technology

  `CONSTRUCTION` | Construction

  `CRYPTO` | Crypto Services and Products (Mining, Exchange, Broker)

  `DRUGS` | Illicit Drugs / Drug Paraphernalia

  `E_COMMERCE` | E-Commerce

  `EDUCATIONAL_SERVICES` | Educational Services

  `EXPORT_IMPORT` | Export / Import Companies

  `FINANCE_INSURANCE` | Other Financial & Insurance Services (Not Referenced
  Elsewhere)

  `FINANCIAL_INSTITUTION` | Financial Institution

  `GAMBLING` | Gaming, Gambling, Casinos, or Sports Betting

  `HEALTH_CARE_SOCIAL_ASSISTANCE` | Health Care and Social Assistance

  `HEDGE_FUND` | Pooled Investment Vehicle / Investment Fund / Hedge Fund

  `INFORMATION` | Information, Communications, and Media

  `INSURANCE` | Insurance

  `INVESTMENT` | Investment

  `MANAGEMENT_OF_COMPANIES_ENTERPRISES` | Management of Companies & Enterprises
  (Holding Companies)

  `MANUFACTURING` | Manufacturing

  `MARKET_MAKER` | Market Maker / Proprietary Trading

  `MINING` | Oil & Gas

  `MONEY_SERVICE_BUSINESS` | Money Services Business / Money Transmitters
  (including ATMs)

  `NON_PROFIT` | Non-Profit, Charity or Political Organizations

  `OTHER_SERVICES` | Other

  `PRECIOUS_METALS` | Jewelry or Precious Metals (Mining, Transportation,
  Dealing or Retail)

  `PROFESSIONAL_SCIENTIFIC_TECHNICAL_SERVICES` | Professional Services
  (Consulting, Legal, Accounting, etc.)

  `PUBLIC_ADMINISTRATION` | Public or Government Services

  `RANSOMWARE` | Ransomware / Facilitators of Ransomware Transactions

  `REAL_ESTATE_RENTAL_LEASING` | Real Estate and Rental and Leasing

  `REGISTERED_INVESTMENT_ADVISOR` | Registered Investment Advisor

  `RETAIL_TRADE` | Retail Trade

  `SHELL_BANK` | Shell Banks or Shell Companies

  `STO_ISSUER` | Security Token Offering (STO) Issuer

  `TRANSPORTATION_WAREHOUSING` | Transportation and Services

  `TRAVEL_TRANSPORT` | Travel, Accomodation or Transport

  `UTILITIES` | Utilities

  `WEAPONS` | Weapons or Arms (Manufacturing, Sales or Transportation)

  `WHOLESALE_TRADE` | Wholesale Trade


  Notes:

  - `INVESTMENT` is only supported by the institution type `TRUST`.

  - All other subtypes are only supported by types `CORPORATION`, `LLC` and
  `PARTNERSHIP`.


  #### Prohibited Institution Subtypes


  Paxos prohibits certain types of business activity (“Prohibited Businesses”)
  in accordance with its Compliance policies.

  The following non-exhaustive list is representative of the type of activity
  that Paxos prohibits on its platform.

  By creating a Paxos Identity, Paxos customers agree not to use Paxos services
  in connection with any of the following Prohibited Businesses.


  - `ADULT_ENTERTAINMENT`

  - `DRUGS`

  - `RANSOMWARE`

  - `SHELL_BANK`

  - `WEAPONS`


  #### Shared Validations Across All Institution Types


  Field | Notes

  ---|---

  cip_id | One of EIN, REGISTRATION_NUMBER, SSN, ITIN. SSN and ITIN are only
  supported for passthrough/revocable entities.

  tax_details | Automatically populated if the cip_id_type is SSN, ITIN or EIN.

  tax_details_not_required | Can be set for non-US institutions where tax
  details are not required.

  metadata | Optional

  ref_id | Optional


  #### Specifying Institution Members and Their Roles


  Field | Notes

  ---|---

  identity_id | Required

  roles | Required.

  ownership | Optional. Must be between 0 and 100

  position | Optional


  Note

  See supported institution types for details on which roles are supported by
  which institution type.


  #### Fields Required for Trusts


  Type | Fields

  ---|---

  Required | name, cip_id, cip_id_type, cip_id_country, institution_type,
  institution_sub_type, business_address, govt_registration_date

  Optional | phone_number, email, incorporation_address, regulation_status,
  trading_type, listed_exchange, ticker_symbol, parent_institution_name,
  regulator_jurisdiction, regulator_name, regulator_register_number


  Notes

  Fields not listed are forbidden in the request. `institution_type` must be set
  to TRUST. `institution_sub_type` must be set to Investment.

  `incorporation_address` is required for Trusts where their cip_id_type is not
  SSN or ITIN.


  ##### Example Request for a Trust

  <!--indentation does not work in swagger code blocks-->

  <pre>

  <code>

  {

  &nbsp;&nbsp;"institution_members": [{

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "33ece656-eef1-43b5-a851-b6b9099089a5",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["GRANTOR"]

  &nbsp;&nbsp;&nbsp;&nbsp;},

  &nbsp;&nbsp;&nbsp;&nbsp;{

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"identity_id":
  "44ece656-eef1-43b5-a851-b6b9099089a6",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"roles": ["TRUSTEE"]

  &nbsp;&nbsp;&nbsp;&nbsp;}],

  &nbsp;&nbsp;"institution_details": {

  &nbsp;&nbsp;&nbsp;&nbsp;"name": "Trust A",

  &nbsp;&nbsp;&nbsp;&nbsp;"business_address": {

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"country": "United States",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"address1": "1 Example St",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"city": "New York",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"province": "NY",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"zip_code": "10001"

  &nbsp;&nbsp;&nbsp;&nbsp;},

  &nbsp;&nbsp;&nbsp;&nbsp;"email": "institution_a@acorp.com",

  &nbsp;&nbsp;&nbsp;&nbsp;"institution_type": "CORPORATION",

  &nbsp;&nbsp;&nbsp;&nbsp;"institution_sub_type": "HEDGE_FUND",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id": "11-1111111",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id_type": "EIN",

  &nbsp;&nbsp;&nbsp;&nbsp;"cip_id_country": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;"govt_registration_date": "2021-04-14T00:00:00Z",

  &nbsp;&nbsp;&nbsp;&nbsp;"incorporation_address": {

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"country": "United States",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"address1": "1 Example St",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"city": "New York",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"province": "NY",

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"zip_code": "10001"

  &nbsp;&nbsp;&nbsp;&nbsp;},

  &nbsp;&nbsp;&nbsp;&nbsp;"regulation_status": "US_REGULATED",

  &nbsp;&nbsp;&nbsp;&nbsp;"trading_type": "PUBLIC",

  &nbsp;&nbsp;&nbsp;&nbsp;"listed_exchange": "NASDAQ",

  &nbsp;&nbsp;&nbsp;&nbsp;"ticker_symbol": "ABC",

  &nbsp;&nbsp;&nbsp;&nbsp;"regulator_name": "SEC",

  &nbsp;&nbsp;&nbsp;&nbsp;"regulator_jurisdiction": "USA",

  &nbsp;&nbsp;&nbsp;&nbsp;"regulator_register_number": "111-111111"

  &nbsp;&nbsp;}

  }

  </code>

  </pre>


  #### Fields Required for Institutions (excluding Trusts and Registered
  Investment Advisors)


  Type | Fields

  ---|---

  Required | name, cip_id, cip_id_type, cip_id_country, institution_type,
  institution_sub_type, business_address, incorporation_address,
  govt_registration_date, regulation_status, trading_type

  Optional | phone_number, email, listed_exchange, ticker_symbol,
  parent_institution_name, regulator_jurisdiction, regulator_name,
  regulator_register_number


  #### Creating Financially Regulated Institutions

  Please refer to the following table for creating institutions which are
  financially regulated.


  regulation_status | Notes

  ---|---

  US_REGULATED | Institution financially regulated in the US

  INTL_REGULATED | Institution financially regulated by an international entity

  NON_REGULATED | Non-financially regulated institution


  Note that each category of `regulation_status` then has additional validations
  tied to `trading type` and other required fields.


  regulation_status | trading_type | fields required | Notes

  ---|---|---|---

  US_REGULATED | PRIVATE | regulator_name, regulator_jurisdiction,
  regulator_register_number | Not publicly traded

  US_REGULATED | PUBLIC | listed_ exchange, ticker_symbol, regulator_name,
  regulator_jurisdiction, regulator_register_number | Publicly traded

  US_REGULATED | PUBLICLY_TRADED_SUBSIDIARY | listed_exchange, ticker_symbol,
  regulator_name, regulator_jurisdiction, regulator_register_number,
  parent_institution_name | Subsidiary of a publicly traded company

  INTL_REGULATED | PRIVATE | regulator_name, regulator_jurisdiction,
  regulator_register_number | Not publicly traded

  INTL_REGULATED | PUBLIC | listed_ exchange, ticker_symbol, regulator_name,
  regulator_jurisdiction, regulator_register_number | Publicly traded

  INTL_REGULATED | PUBLICLY_TRADED_SUBSIDIARY | listed_exchange, ticker_symbol,
  regulator_name, regulator_jurisdiction, regulator_register_number,
  parent_institution_name | Subsidiary of a publicly traded company

  NON_REGULATED | PRIVATE | PRIVATE | Not publicly traded

  NON_REGULATED | PUBLIC | listed_exchange, ticker_symbol | Publicly traded


  #### Fields required for Registered Investment Advisors (RIA)


  RIAs are a special sub-type of Institution. Usage of this sub-type requires
  prior authorization and approval from Paxos.


  Notes

  `institution_sub_type` must be set to REGISTERED_INVESTMENT_ADVISOR. The list
  of required and optional fields below varies slightly from other supported
  institutions

  while certain fields are optional (e.g. trading_type), if they are specified
  in the request, their input will been validated


  Type | Fields

  ---|---

  Required | name, cip_id, cip_id_type, cip_id_country, institution_type,
  institution_sub_type, business_address, regulation_status,
  regulator_jurisdiction, regulator_name, regulator_register_number

  Optional | phone_number, email, listed_exchange, ticker_symbol,
  parent_institution_name, incorporation_address, govt_registration_date,
  trading_type
api:
  file: paxos.json
  operationId: CreateIdentity
hidden: false
---
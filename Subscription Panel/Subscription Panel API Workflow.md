1. Subscription Panel application loads.
2. User clicks on either landing or the Subscription Panel calls **GET**`/Offers`. Sends `offerGroupId` and postal code to fetch details.
3. Subscription Panel then calls **POST**`/subscriptionCost` to fetch current taxes and cost.
4. Subscription Panel calls **GET**`/user` to check whether the user already exists. If the user does not already exist, it calls creates the user via **POST**`/user`.
5. User enters the address information. Then, Subscription Panel calls **GET**/address/standardization to standardize the current address.
6. Subscription Panel calls **POST**`/Subscriptions/ActiveCheck` to check whether this user already has an active subscription. If an active subscription exists, it returns an error.
7. Subscription Panel renders iframe with the edgil Javascript, which in turn calls:
    - **POST**/`Billing/PaymentSession/StartPaymentSession` - opens the iframe and generates a token
    - **POST**`/Billing/PaymentSession/EndPaymentSession` - saves credit card information and payment system
8. User clicks submit in Subscription Panel, and the Subscription Panel calls **POST**`/Subscriptions` to create the new subscription.

<!-- --------------------------------------------------------------------- -->

## Offers

> **GET** `/Offers`

This endpoint checks for current the current offers.

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Query string | postalCode | integer | Y | Postal code |
| Query string | request.offerGroupId  | integer | Y | Offer Group ID |

### Request example

The following is a cURL request example:

```bash
curl \
-X GET 'https://test.subscriberconcierge.com/Offers?request.postalCode=00000&request.offerGroupId=6' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: MG2GroupStripe' \
--header 'X-ClientCode: DTI' \
--header 'X-PaperCode: MAA' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: Bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 0' 
```

### Response example

The following is a json example response from the `/Offers` endpoint.

```json
{
  "Code": 200,
  "Errors": [
    {
      "Message": "Sorry! there are no offers available for the entered zip code.",
      "Code": "Offers23",
      "Type": {
        "Id": 0,
        "Code": "Validation"
      },
      "ErrorSource": null
    }
  ],
  "Result": null,
  "SessionId": "aef72d8a-7fb8-4d8b-9207-6195b85a5fe4",
  "RequestId": "0"
}
```

<!-- --------------------------------------------------------------------- -->

## Subscription cost

> **POST** `/subscription/cost`

This endpoint checks the current cost and tax for a particular offer.

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Request body |  | integer | Y | JSON object (see request example below). |

### Request example

The following is a cURL request example:

```bash
curl \
-X POST 'https://test.subscriberconcierge.com/Subscriptions/Cost' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: MG2GroupStripe' \
--header 'X-ClientCode: DTI' \
--header 'X-PaperCode: MAA' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 0' \
-d '{

    "OfferId": "9",
    "OfferGroupId": "6",
    "Products": [
        {
            "ExternalProductId": "100079",
            "MerchantProductId": "100079",
            "ProductId": "100079",
            "ProductQuantity": "1"
        }
    ]
}'
```

### Response example

The following is a json example response from the `Subscriptions/Cost` endpoint:

```json
{
    "SubscriptionCost": 31.99,
    "Taxes": null,
    "ActivationFee": 0.0,
    "TotalAmount": 31.99
}
```

<!-- --------------------------------------------------------------------- -->

## User information

> **GET** `/User`

This end point checks whether the user's email already exists.

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Query string | request.email | string | Y | Email address that is checked. |
| Query string | request.onlyActive  | Boolean | Y | If `TRUE`, only checks active subscriptions. If `FALSE`, checks both active and inactive subscriptions. |

### Request

The following is a cURL request example:

```bash
curl \
-X GET 'https://test.subscriberconcierge.com/User?request.email=nee1%40yopmail.com&request.onlyActive=true' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: GCI' \
--header 'X-ClientCode: WestPalmBeach' \
--header 'X-PaperCode: PO' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 1'\
```

### Response

The following is a json example response from the `/user` endpoint:

```json
{
  "Code": 200,
  "Errors": [],
  "Result": {
    "Users": [
      {
        "RegistrationId": 30,
        "LoginName": "nee1@yopmail.coms",
        "LoginPassword": null,
        "CustomerRegistrationId": "594e74f6-31de-ea11-b4e2-005056b47960",
        "EncryptedCustomerRegistrationId": null,
        "FirstName": "Neetha",
        "LastName": "Sam",
        "Email": "nee1@yopmail.coms",
        "Gender": null,
        "PhoneAc": null,
        "PhoneEx": null,
        "PhoneExt": null,
        "Phone": null,
        "MobilePhone": null,
        "OptInEVantageSubscriberRewards": false,
        "OptInSpecialOffers": false,
        "OptInContestAndPromotions": false,
        "OptInPaperlessBilling": false,
        "OptInEEdition": false,
        "OptInEEditionEmailNotification": false,
        "OptInSubscriberDiscounts": false,
        "OptInAdvertiserEmails": false,
        "MemberEvent": false,
        "ContentEngagement": false,
        "SUBCOM": false,
        "Survey": false,
        "AccountUpdates": false,
        "DateOfBirth": null,
        "BirthYear": null,
        "AcceptsEmailOffers": null,
        "AcceptsEmailAds": null,
        "AcceptsEmailPromotions": null,
        "IsOkToEmail": null,
        "IsOkToPhone": null,
        "IsOkToMail": null,
        "AcceptsEENotification": null,
        "ChangeDate": "2020-12-22T20:31:11.227",
        "DateRegistered": null,
        "Photos": null,
        "IsSocial": false,
        "DisplayName": null,
        "AgreeToTerms": false,
        "OptOutMarketing": false,
        "Photo": null,
        "VerificationCode": null,
        "Verified": true,
        "AuthSystem": {
          "AuthSystemId": 2,
          "AuthSystemCode": "Firefly",
          "AuthSystemName": "Firefly"
        },
        "UserState": {
          "UserStateId": 3,
          "UserStateCode": "Standard"
        },
        "BounceType": null
      },
      {
        "RegistrationId": 539,
        "LoginName": "nee1@yopmail.com",
        "LoginPassword": null,
        "CustomerRegistrationId": "34baebc8-8301-eb11-a19e-005056b47960",
        "EncryptedCustomerRegistrationId": null,
        "FirstName": "Neetha",
        "LastName": "Rangaswamy",
        "Email": "nee1@yopmail.com",
        "Gender": null,
        "PhoneAc": null,
        "PhoneEx": null,
        "PhoneExt": null,
        "Phone": null,
        "MobilePhone": null,
        "OptInEVantageSubscriberRewards": false,
        "OptInSpecialOffers": false,
        "OptInContestAndPromotions": false,
        "OptInPaperlessBilling": false,
        "OptInEEdition": false,
        "OptInEEditionEmailNotification": false,
        "OptInSubscriberDiscounts": false,
        "OptInAdvertiserEmails": false,
        "MemberEvent": false,
        "ContentEngagement": false,
        "SUBCOM": false,
        "Survey": false,
        "AccountUpdates": false,
        "DateOfBirth": null,
        "BirthYear": null,
        "AcceptsEmailOffers": null,
        "AcceptsEmailAds": null,
        "AcceptsEmailPromotions": null,
        "IsOkToEmail": null,
        "IsOkToPhone": null,
        "IsOkToMail": null,
        "AcceptsEENotification": null,
        "ChangeDate": "2021-01-26T14:59:01.583",
        "DateRegistered": null,
        "Photos": null,
        "IsSocial": false,
        "DisplayName": null,
        "AgreeToTerms": false,
        "OptOutMarketing": false,
        "Photo": null,
        "VerificationCode": null,
        "Verified": true,
        "AuthSystem": {
          "AuthSystemId": 2,
          "AuthSystemCode": "Firefly",
          "AuthSystemName": "Firefly"
        },
        "UserState": {
          "UserStateId": 3,
          "UserStateCode": "Standard"
        },
        "BounceType": null
      }
    ],
    "TotalUsersFound": 2
  },
  "SessionId": "3bc55dd6-f4c1-48e0-9d65-f2cd438d7fd6",
  "RequestId": "1"
}
```

<!-- --------------------------------------------------------------------- -->

## Create user

> **POST** `/User`

This endpoint creates the user **if** the user doesn't already exist.

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Request body |  | integer | Y | JSON object (see request example below). |

### Request example

The following is a cURL request example:

```bash
curl \
-X POST 'https://test.subscriberconcierge.com/User' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: GCI' \
--header 'X-ClientCode: WestPalmBeach' \
--header 'X-PaperCode: PO' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 0' \
-d '{
  "Email": "johnnySilverhands@fakeemail.com",
  "Password": "fakepassword",
  "CreationMode": 0,
  "FirstName": "Johnny",
  "LastName": "Silverhands",
  "VerifyEmail": true
}'
```
### Response example

The following is a json example response from the `/User` endpoint:

```json
{
  "Code": 200,
  "Errors": [],
  "Result": {
    "CustomerRegistrationId": "b85d673a-0a68-eb11-a19e-005056b47960",
    "EncryptedCustomerRegistrationId": null,
    "Mg2RegistrationId": 712,
    "RegistrationVerificationId": null,
    "Tokens": null
  },
  "SessionId": "76d1ccfe-c5a3-4bd4-ad98-013ae7703014",
  "RequestId": "0"
}
```

<!-- --------------------------------------------------------------------- -->

## Address standardization

> **GET** `/Address/Standardization`

This endpoint uses a service to standardize the entered address.

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Query string | request.address.address | string | Y | Street address that is checked. |
| Query string | request.city | string | Y | City of address that is checked. |
| Query string | request.state | string | Y | State of address that is checked. |
| Query string | request.postalCode | number | Y | Postal code of address that is checked. |

### Request example

The following is a cURL request example:

```bash
curl \
-X GET 'https://test.subscriberconcierge.com/Address/Standardization?request.address.address=1600%20Pennsylvania%20Avenue%20NW&request.address.city=DC&request.address.state=Washington&request.address.postalCode=20005&request.address.country=USA' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: GCI' \
--header 'X-ClientCode: WestPalmBeach' \
--header 'X-PaperCode: PO' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 2'
```

### Response example

The following is a json example response from the `/Address/Standardization` endpoint:

```json
{
  "Code": 200,
  "Errors": [],
  "Result": {
    "IsValidAddress": true,
    "Reason": "",
    "Address": {
      "Address": "1600 Pennsylvania Ave NW",
      "Address2": null,
      "HouseNumber": "1600",
      "StreetName": "Pennsylvania",
      "StreetSuffix": "Ave",
      "PreDirect": "",
      "PostDirect": "NW",
      "AptUnit": "",
      "AptNumber": "",
      "UnitType": "",
      "District": null,
      "City": "Washington",
      "State": "DC",
      "ZipCode": "20500",
      "ZipCode4": "0005",
      "DPVCode": "AABB",
      "SuiteStatus": "V",
      "Suite": "",
      "DeliveryPointCheckDigit": "8",
      "DPVFootnotes": "AABB",
      "DeliveryPointCode": "00",
      "CountyFips": "11001",
      "LockBox": "",
      "RouteService": "",
      "Country": "US",
      "CountryName": null,
      "Msa": "",
      "CarrierRoute": "C000",
      "ParsedAddressKey": "0000001600000AVENWPENNSYLVNA000000020500",
      "PakHash": "f0bc64e5cd67d63152e4617f13a0b04b",
      "StandardizationError": " ",
      "StandardizationErrorMessage": "No Error",
      "StandardizationResult": "AC01,AC02,AC03,AS01",
      "Latitude": "38.897199",
      "Longitude": "-77.036548",
      "CensusBlock": "1031",
      "CensusTract": "006202",
      "GeoCoderResult": "GS01",
      "ParsedGarbage": "",
      "AddressTypeCode": "S",
      "AddressType": "Street",
      "DependentLocality": null
    },
    "Suggestions": []
  },
  "SessionId": "2ad26292-4bfb-4f2d-8300-11efadc626ff",
  "RequestId": "2"
}
```

<!-- --------------------------------------------------------------------- -->

## Active check

> **POST** `/Subscription/ActiveCheck` 

This endpoint checks the subscriber has an active subscription.

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Request body |  | integer | Y | JSON object (see request example below). |

### Request example

The following is a cURL request example:

```bash
curl \
-X POST 'https://test.subscriberconcierge.com/Subscriptions/ActiveCheck' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: GCI' \
--header 'X-ClientCode: WestPalmBeach' \
--header 'X-PaperCode: PO' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 0' \
-d '{
  "LastName": "Sam",
  "DeliveryHouseNumber": "561",
  "DeliveryStreetName": "Island",
  "DeliveryAptUnit": "",
  "DeliveryPostalCode": "33480",
  "Phone": "9999999999",
  "OfferId": 9,
  "Products": [
    {
      "ProductId": 100079,
      "ExternalProductId": "100079",
      "MerchantProductId": null
    }
  ],
  "StartType": 0
}'

```

### Response example

The following is a json example response from the `Subscriptions/ActiveCheck` endpoint:

```json
{
  "Code": 200,
  "Errors": [],
  "Result": {
    "ProductsExist": false,
    "ExistingProductIds": []
  },
  "SessionId": "851f643f-f389-4b2a-87e9-b8c01aa54998",
  "RequestId": "0"
}
```
<!-- --------------------------------------------------------------------- -->

## Start payment session

> **POST** `/Billing/PaymentSession/StartPaymentSession`

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Request body |  | integer | Y | JSON object (see request example below). |

### Request example

The following is a cURL request example:

```bash
curl \
-X POST 'https://test.subscriberconcierge.com/Billing/PaymentSession/StartPaymentSession' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: GCI' \
--header 'X-ClientCode: WestPalmBeach' \
--header 'X-PaperCode: PO' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 0' \
-d '{
  "EventData": {
    "EventId": 0,
    "DateLocal": "0001-01-01T00:00:00",
    "EventTypeId": null,
    "EventTypeCode": null,
    "AddDate": null,
    "EditDate": null,
    "Status": null,
    "ReplyId": null,
    "ReplyText": null,
    "RetryCount": null,
    "UserIPAddress": "71.230.24.62",
    "ComplaintCode": null,
    "SubscriptionId": null,
    "SubscriberId": null,
    "SubscriptionProductId": null,
    "ExternalSubscriptionId": null,
    "ExternalSubscriberId": null,
    "ExternalSubscriptionProductId": null,
    "SubscriberNumber": null,
    "PaperCode": "PO",
    "EditionCode": null,
    "AccountNumber": null,
    "HHId": null,
    "FirstName": null,
    "LastName": null,
    "Title": null,
    "CompanyName": null,
    "DeliveryAddressId": null,
    "DeliveryAddress1": null,
    "DeliveryAddress2": null,
    "DeliveryCity": null,
    "DeliveryCityCode": null,
    "DeliveryState": null,
    "DeliveryZip": null,
    "DeliveryZip5": null,
    "DeliveryZip4": null,
    "DeliveryHouseNumber": null,
    "DeliveryPreDirect": null,
    "DeliveryStreetName": null,
    "DeliveryStreetSuffix": null,
    "DeliveryPostDirect": null,
    "DeliveryUnitType": null,
    "DeliveryRoute": null,
    "FipsCode": null,
    "MSACode": null,
    "DMACode": null,
    "Latitude": null,
    "Longitude": null,
    "DeliveryUnitNumber": null,
    "BillingTitle": null,
    "BillingCompanyName": null,
    "BillingFirstName": null,
    "BillingLastName": null,
    "BillingPhone": null,
    "BillingPhoneAlternative": null,
    "BillingEmail": null,
    "BillingAddressId": null,
    "BillingAddress1": null,
    "BillingAddress2": null,
    "BillingCity": null,
    "BillingCityCode": null,
    "BillingState": null,
    "BillingZip": null,
    "BillingZip5": null,
    "BillingZip4": null,
    "BillingHouseNumber": null,
    "BillingPreDirect": null,
    "BillingStreet": null,
    "BillingStreetSuffix": null,
    "BillingPostDirect": null,
    "BillingUnitType": null,
    "BillingUnitNumber": null,
    "Phone": null,
    "PhoneAlternative": null,
    "Email": null,
    "EmailNew": null,
    "SubscriberStatus": null,
    "ServiceCode": "SMTWTFS",
    "ServiceCodeNew": null,
    "ServiceTypeId": 79,
    "ServiceTypeIdNew": null,
    "Copies": null,
    "BillingNumber": null,
    "PromoCode": null,
    "PromoSource": null,
    "PromoSubSource": null,
    "PromoCert": null,
    "PromoCredit": null,
    "DateStart": null,
    "DateStop": null,
    "StartSource": null,
    "StartReason": null,
    "StopSource": null,
    "StopReason": null,
    "RateCode": null,
    "PlanCode": null,
    "CurrentRate": null,
    "CurrentBalance": null,
    "BillingCycle": null,
    "CreditCardType": null,
    "CreditCardNumber": null,
    "CreditCardExpirationMonth": null,
    "CreditCardExpirationYear": null,
    "CreditCardOwnerName": null,
    "UALFlag": null,
    "UALNumber": null,
    "DeliveryAddressStandarizationError": null,
    "BillingAddressStandarizationError": null,
    "LoginName": null,
    "LoginPassword": null,
    "LoginNameNew": null,
    "LoginPasswordNew": null,
    "EZPayGiftType": null,
    "UseDeliveryAddressForBillingAddress": null,
    "Comments": null,
    "DateEffective": null,
    "ComplaintMemo": null,
    "OrigStartDate": null,
    "SundayPlus": null,
    "RegistrationId": null,
    "ParentEventId": null,
    "OperatorId": null,
    "DateLastPay": null,
    "DatePaidThru": null,
    "LastPayAmount": null,
    "MiscTinyInt1": null,
    "PremiumId": null,
    "MagazineId": null,
    "PromotionId": null,
    "OfferId": 9,
    "OfferGroupId": 6,
    "EmailOffers": null,
    "PaymentAmount": 31.99,
    "TipAmount": null,
    "EZPayFlag": true,
    "OriginalEventId": null,
    "ReturnToVendor": null,
    "CSRProcessDate": null,
    "PhoneType": null,
    "CreditCardSecurityCode": null,
    "CreditCardTransactionId": null,
    "CreditCardAuthorizationNumber": null,
    "DeliveryInstructions": null,
    "DeliveryDisctrict": null,
    "MiscCode": null,
    "DeliveryDistrictId": null,
    "BankAccountType": null,
    "BankAccountNumber": null,
    "RoutingNumber": null,
    "BankInstitution": null,
    "OperatorInitials": null,
    "GiftFlag": null,
    "Weeks": null,
    "Publication": null,
    "BusinessFlag": null,
    "FullName": null,
    "MiddleName": null,
    "NameSuffix": null,
    "NameAttention": null,
    "PremiumCode": null,
    "MagazineCode": null,
    "DNC": null,
    "Unlisted": null,
    "BillCode": null,
    "TransactionCode": null,
    "PaymentType": null,
    "DwellingType": null,
    "SubscriptionType": null,
    "DeliveryRoute2": null,
    "ExportedToNP": null,
    "NewspaperId": null,
    "DonationAmount": null,
    "PastDuePaymentAmount": null,
    "PlanOfferCode": null,
    "CSRId": null,
    "CSRIdEdit": null,
    "CurrentAmount": null,
    "eEditionAmount": null,
    "ChargeFlag": null,
    "ProductId": null,
    "RequestPageUrl": "https://test-checkout3.palmbeachpost.com/",
    "AutoRenewTip": null,
    "AutoRenewDonation": null,
    "PaymentSelectedAmount": null,
    "AddressID": null,
    "OccupantID": null,
    "DTISubscriptionID": null,
    "CampaignID": null,
    "ActivationFee": null,
    "SubscriptionAmount": 31.99,
    "TaxAmount": null,
    "CountryName": null,
    "CreditCardToken": null,
    "Currency": null,
    "CountryCode": null,
    "InternationalPhoneNumber": null,
    "Sub3Code": null,
    "eEditionAccess": null,
    "CustomerRegistrationId": null,
    "SolicitorQueueId": null,
    "ActivationCode": null,
    "VindiciaAccountId": null,
    "VindiciaAutobillId": null,
    "BillingSystemId": null,
    "BillingSystemAccountId": null,
    "SessionId": "Sq_ukFv3vnSnrgtGrhoQ77oRgyoTk4cp",
    "SessionStart": null,
    "SessionEnd": null,
    "eEditionInstantAccessFlag": null,
    "eEditionInstantAccessDays": null,
    "RequestId": null,
    "RequestBody": null,
    "ComplaintId": null,
    "TemporaryStopId": null,
    "SourceSystem": null,
    "CallerId": null,
    "PaymentMethodId": null,
    "TrackingCodes": null,
    "Commission": null,
    "EditSourceSystem": null,
    "Reason": null,
    "Resolution": null,
    "SalesRepresentativeCode": null,
    "MoveId": null,
    "RewardCode": null,
    "EntitlementId": null,
    "StopId": null,
    "MessageType": null,
    "UpdateStartDate": null,
    "UpdateStopDate": null,
    "SolicitorUserId": null,
    "SolicitorUserCode": null,
    "SolicitorVendorId": null,
    "SolicitorVendorName": null,
    "SolicitorSmartSegment": null,
    "ServiceTypeName": "7 Day Delivery",
    "CustomCode1": null,
    "CustomCode2": null,
    "CustomCode3": null,
    "CustomCode4": null,
    "CustomCode5": null,
    "CustomCode6": null,
    "CustomCode7": null,
    "CustomCode8": null,
    "CustomCode9": null,
    "CustomCode10": null,
    "BillingSystemCode1": null,
    "BillingSystemCode2": null,
    "BillingSystemCode3": null,
    "BillingSystemCode4": null,
    "BillingSystemCode5": null,
    "BillingSystemCode6": null,
    "BillingSystemCode7": null,
    "BillingSystemCode8": null,
    "BillingSystemCode9": null,
    "BillingSystemCode10": null,
    "BillingSystemCode11": null,
    "BillingSystemCode12": null,
    "AttachmentFiles": null,
    "BaseProductName": null,
    "NextBillingCyclePrice": null,
    "NextBillingDate": null,
    "PaymentMethodType": null,
    "BillingPlanDescription": null,
    "LegacyAccountNumber": null,
    "MarketCode": null,
    "PresentationName": null,
    "CouponCode": null,
    "VacationSplitId": null,
    "CircSystemId": null,
    "CheckOutStep": "",
    "AddDateLocal": null,
    "EditDateLocal": null,
    "OfferDisplayText": null,
    "Tenant": null,
    "ServerName": null,
    "LocationId": null,
    "LocationName": null,
    "Notes": null,
    "EncryptedEventId": null,
    "PromotionCode": null,
    "PromotionName": null,
    "OfferName": null,
    "OfferGroupName": null,
    "TermsAndConditionsId": 0,
    "EngagementRate": 0,
    "EngagementRatePercentile": 0,
    "TrialSubscription": null
  },
  "ProviderRequest": {
    "PageName": "mg2sp_hpp_form_simple"
  }
}'
```

### Response example

The following is a json example response from the `/Billing/PaymentSession/StartPaymentSession` endpoint:

```json
{
  "Code": 200,
  "Errors": [],
  "Result": {
    "PaymentSessionId": null,
    "ProviderResponse": {
      "EdgilPaywayRequestId": "1661685794"
    },
    "EventId": 201375
  },
  "SessionId": "b8f307d6-a6ab-4e8e-8733-1a7e5e1d1bff",
  "RequestId": "0"
}
```
<!-- --------------------------------------------------------------------- -->

## End payment session

> **POST** `/Billing/PaymentSession/EndPaymentSession`

## Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Request body |  | integer | Y | JSON object (see request example below). |

## Request example

The following is a cURL request example:

```bash
curl \
-X POST 'https://test.subscriberconcierge.com/Billing/PaymentSession/EndPaymentSession' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: GCI' \
--header 'X-ClientCode: WestPalmBeach' \
--header 'X-PaperCode: PO' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 0' \
-d '{
  "PaymentSessionId": null,
  "ProviderRequest": {
    "RequestId": "1101246335"
  },
  "EventData": {
    "EventId": 0,
    "DateLocal": "0001-01-01T00:00:00",
    "EventTypeId": null,
    "EventTypeCode": null,
    "AddDate": null,
    "EditDate": null,
    "Status": null,
    "ReplyId": null,
    "ReplyText": null,
    "RetryCount": null,
    "UserIPAddress": "71.230.24.62",
    "ComplaintCode": null,
    "SubscriptionId": null,
    "SubscriberId": null,
    "SubscriptionProductId": null,
    "ExternalSubscriptionId": null,
    "ExternalSubscriberId": null,
    "ExternalSubscriptionProductId": null,
    "SubscriberNumber": null,
    "PaperCode": "PO",
    "EditionCode": null,
    "AccountNumber": null,
    "HHId": null,
    "FirstName": "Neetha",
    "LastName": "Sam",
    "Title": null,
    "CompanyName": null,
    "DeliveryAddressId": null,
    "DeliveryAddress1": "561 Island Dr",
    "DeliveryAddress2": null,
    "DeliveryCity": "Palm Beach",
    "DeliveryCityCode": null,
    "DeliveryState": "FL",
    "DeliveryZip": "33480",
    "DeliveryZip5": null,
    "DeliveryZip4": null,
    "DeliveryHouseNumber": null,
    "DeliveryPreDirect": null,
    "DeliveryStreetName": null,
    "DeliveryStreetSuffix": null,
    "DeliveryPostDirect": null,
    "DeliveryUnitType": null,
    "DeliveryRoute": null,
    "FipsCode": null,
    "MSACode": null,
    "DMACode": null,
    "Latitude": null,
    "Longitude": null,
    "DeliveryUnitNumber": null,
    "BillingTitle": null,
    "BillingCompanyName": null,
    "BillingFirstName": null,
    "BillingLastName": null,
    "BillingPhone": "9999999999",
    "BillingPhoneAlternative": null,
    "BillingEmail": null,
    "BillingAddressId": null,
    "BillingAddress1": "561 Island Dr",
    "BillingAddress2": null,
    "BillingCity": "Palm Beach",
    "BillingCityCode": null,
    "BillingState": "FL",
    "BillingZip": "33480",
    "BillingZip5": null,
    "BillingZip4": null,
    "BillingHouseNumber": null,
    "BillingPreDirect": null,
    "BillingStreet": null,
    "BillingStreetSuffix": null,
    "BillingPostDirect": null,
    "BillingUnitType": null,
    "BillingUnitNumber": null,
    "Phone": "9999999999",
    "PhoneAlternative": null,
    "Email": "testneetha1@yopmail.com",
    "EmailNew": null,
    "SubscriberStatus": null,
    "ServiceCode": "SMTWTFS",
    "ServiceCodeNew": null,
    "ServiceTypeId": 79,
    "ServiceTypeIdNew": null,
    "Copies": null,
    "BillingNumber": null,
    "PromoCode": null,
    "PromoSource": null,
    "PromoSubSource": null,
    "PromoCert": null,
    "PromoCredit": null,
    "DateStart": null,
    "DateStop": null,
    "StartSource": null,
    "StartReason": null,
    "StopSource": null,
    "StopReason": null,
    "RateCode": null,
    "PlanCode": null,
    "CurrentRate": null,
    "CurrentBalance": null,
    "BillingCycle": null,
    "CreditCardType": null,
    "CreditCardNumber": null,
    "CreditCardExpirationMonth": null,
    "CreditCardExpirationYear": null,
    "CreditCardOwnerName": null,
    "UALFlag": null,
    "UALNumber": null,
    "DeliveryAddressStandarizationError": null,
    "BillingAddressStandarizationError": null,
    "LoginName": null,
    "LoginPassword": null,
    "LoginNameNew": null,
    "LoginPasswordNew": null,
    "EZPayGiftType": null,
    "UseDeliveryAddressForBillingAddress": null,
    "Comments": null,
    "DateEffective": null,
    "ComplaintMemo": null,
    "OrigStartDate": null,
    "SundayPlus": null,
    "RegistrationId": null,
    "ParentEventId": null,
    "OperatorId": null,
    "DateLastPay": null,
    "DatePaidThru": null,
    "LastPayAmount": null,
    "MiscTinyInt1": null,
    "PremiumId": null,
    "MagazineId": null,
    "PromotionId": null,
    "OfferId": 9,
    "OfferGroupId": 6,
    "EmailOffers": null,
    "PaymentAmount": 34.23,
    "TipAmount": null,
    "EZPayFlag": true,
    "OriginalEventId": null,
    "ReturnToVendor": null,
    "CSRProcessDate": null,
    "PhoneType": null,
    "CreditCardSecurityCode": null,
    "CreditCardTransactionId": null,
    "CreditCardAuthorizationNumber": null,
    "DeliveryInstructions": null,
    "DeliveryDisctrict": null,
    "MiscCode": null,
    "DeliveryDistrictId": null,
    "BankAccountType": null,
    "BankAccountNumber": null,
    "RoutingNumber": null,
    "BankInstitution": null,
    "OperatorInitials": null,
    "GiftFlag": null,
    "Weeks": null,
    "Publication": null,
    "BusinessFlag": null,
    "FullName": "Neetha Sam",
    "MiddleName": null,
    "NameSuffix": null,
    "NameAttention": null,
    "PremiumCode": null,
    "MagazineCode": null,
    "DNC": null,
    "Unlisted": null,
    "BillCode": null,
    "TransactionCode": null,
    "PaymentType": null,
    "DwellingType": null,
    "SubscriptionType": null,
    "DeliveryRoute2": null,
    "ExportedToNP": null,
    "NewspaperId": null,
    "DonationAmount": null,
    "PastDuePaymentAmount": null,
    "PlanOfferCode": null,
    "CSRId": null,
    "CSRIdEdit": null,
    "CurrentAmount": null,
    "eEditionAmount": null,
    "ChargeFlag": null,
    "ProductId": null,
    "RequestPageUrl": "https://test-checkout3.palmbeachpost.com/",
    "AutoRenewTip": null,
    "AutoRenewDonation": null,
    "PaymentSelectedAmount": null,
    "AddressID": null,
    "OccupantID": null,
    "DTISubscriptionID": null,
    "CampaignID": null,
    "ActivationFee": null,
    "SubscriptionAmount": 31.99,
    "TaxAmount": 2.24,
    "CountryName": null,
    "CreditCardToken": null,
    "Currency": null,
    "CountryCode": "US",
    "InternationalPhoneNumber": null,
    "Sub3Code": null,
    "eEditionAccess": null,
    "CustomerRegistrationId": null,
    "SolicitorQueueId": null,
    "ActivationCode": null,
    "VindiciaAccountId": null,
    "VindiciaAutobillId": null,
    "BillingSystemId": null,
    "BillingSystemAccountId": null,
    "SessionId": "9egRa8Azo_VOJR5uP4qbFVG4RgeKhqbG",
    "SessionStart": null,
    "SessionEnd": null,
    "eEditionInstantAccessFlag": null,
    "eEditionInstantAccessDays": null,
    "RequestId": null,
    "RequestBody": null,
    "ComplaintId": null,
    "TemporaryStopId": null,
    "SourceSystem": null,
    "CallerId": null,
    "PaymentMethodId": null,
    "TrackingCodes": null,
    "Commission": null,
    "EditSourceSystem": null,
    "Reason": null,
    "Resolution": null,
    "SalesRepresentativeCode": null,
    "MoveId": null,
    "RewardCode": null,
    "EntitlementId": null,
    "StopId": null,
    "MessageType": null,
    "UpdateStartDate": null,
    "UpdateStopDate": null,
    "SolicitorUserId": null,
    "SolicitorUserCode": null,
    "SolicitorVendorId": null,
    "SolicitorVendorName": null,
    "SolicitorSmartSegment": null,
    "ServiceTypeName": "7 Day Delivery",
    "CustomCode1": null,
    "CustomCode2": null,
    "CustomCode3": null,
    "CustomCode4": null,
    "CustomCode5": null,
    "CustomCode6": null,
    "CustomCode7": null,
    "CustomCode8": null,
    "CustomCode9": null,
    "CustomCode10": null,
    "BillingSystemCode1": null,
    "BillingSystemCode2": null,
    "BillingSystemCode3": null,
    "BillingSystemCode4": null,
    "BillingSystemCode5": null,
    "BillingSystemCode6": null,
    "BillingSystemCode7": null,
    "BillingSystemCode8": null,
    "BillingSystemCode9": null,
    "BillingSystemCode10": null,
    "BillingSystemCode11": null,
    "BillingSystemCode12": null,
    "AttachmentFiles": null,
    "BaseProductName": null,
    "NextBillingCyclePrice": null,
    "NextBillingDate": null,
    "PaymentMethodType": null,
    "BillingPlanDescription": null,
    "LegacyAccountNumber": null,
    "MarketCode": null,
    "PresentationName": null,
    "CouponCode": null,
    "VacationSplitId": null,
    "CircSystemId": null,
    "CheckOutStep": "04_billing_completed",
    "AddDateLocal": null,
    "EditDateLocal": null,
    "OfferDisplayText": null,
    "Tenant": null,
    "ServerName": null,
    "LocationId": null,
    "LocationName": null,
    "Notes": null,
    "EncryptedEventId": null,
    "PromotionCode": null,
    "PromotionName": null,
    "OfferName": null,
    "OfferGroupName": null,
    "TermsAndConditionsId": 0,
    "EngagementRate": 0,
    "EngagementRatePercentile": 0,
    "TrialSubscription": null
  }
}'
```

## Response example

The following is a json example response from the `/Billing/PaymentSession/EndPaymentSession` endpoint:

```json
{
  "Code": 200,
  "Errors": [],
  "Result": {
    "PaymentSessionId": null,
    "ProviderResponse": {
      "PaymentSessionId": "1101246335",
      "RequestId": 1101246335,
      "Token": "037641186",
      "AccountNumber": "411111******1111",
      "Expiration": "1223",
      "PaymentType": 1,
      "First": "Neetha12",
      "Last": "Sam112"
    },
    "EventId": 201376
  },
  "SessionId": "9695efc2-f6d9-4f23-a529-bb8669c2574f",
  "RequestId": "0"
}
```

## Create subscription

This endpoint creates the subscription after the user selects submit.

> **POST** /Subscriptions

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
-------------- | --------- | ----- | -------- | ----------
| Header | X-MediaGroupCode | string | Y | Code that designates the circulation system. |
| Header | X-ClientCode | string | Y | Code that designates the client. | 
| Header | X-PaperCode | string | Y | Code that designates the newspaper. |
| Header | X-SourceSystem | string | Y | Code that designates the application. |
| Header | Authorization | string | Y | Authorization token. |
| Header | X-RequestId | integer | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended) |
| Request body |  | integer | Y | JSON object (see request example below). |

### Request example

The following is a cURL request example:

```bash
curl \
-X POST 'https://test.subscriberconcierge.com/Subscriptions' \
--header 'Content-Type: application/json' \
--header 'Accept: application/json' \
--header 'X-MediaGroupCode: MG2GroupStripe' \
--header 'X-ClientCode: DTI' \
--header 'X-PaperCode: MAA' \
--header 'X-SourceSystem: {APPLICATION_NAME}' \
--header 'Authorization: bearer {YOUR_TOKEN}' \
--header 'X-RequestId: 0' \
-d '{
  "CustomerRegistrationId": "18928a75-6d65-eb11-a19e-005056b47960",
  "EmailAddress": "testnathan@yopmail.com",
  "OfferId": 9,
  "PromotionId": 0,
  "PromotionCode": null,
  "OfferGroupId": 6,
  "GiftId": 0,
  "DeliveryAddress": {
    "AddressId": 0,
    "ExternalAddressId": null,
    "FullName": "Nathan Test",
    "FirstName": "Nathan",
    "LastName": "Test",
    "Company": "",
    "Address": "561 Island Dr",
    "HouseNumber": null,
    "StreetName": null,
    "StreetSuffix": null,
    "PreDirect": null,
    "PostDirect": null,
    "AptNumber": null,
    "AptUnit": "",
    "UnitType": null,
    "District": null,
    "City": "Palm Beach",
    "CityCode": null,
    "State": "FL",
    "ZipCode": "33480",
    "ZipCode4": null,
    "DPVCode": null,
    "SuiteStatus": null,
    "DeliveryPointCheckDigit": null,
    "DPVFootnotes": null,
    "DeliveryPointCode": null,
    "CountyFips": null,
    "Msa": null,
    "PakHash": null,
    "ParsedAddressKey": null,
    "StandardizationError": null,
    "StandardizationResult": null,
    "Latitude": null,
    "Longitude": null,
    "CensusBlock": null,
    "CensusTract": null,
    "GeoCoderResult": null,
    "CarrierRoute": null,
    "Country": "",
    "CountryCode": "US",
    "PhoneAC": null,
    "PhoneEX": null,
    "PhoneEXT": null,
    "Phone": "9999999999",
    "Route": null,
    "Title": null
  },
  "BillingAddress": {
    "AddressId": 0,
    "ExternalAddressId": null,
    "FullName": "Neetha Sam",
    "FirstName": "Neetha",
    "LastName": "Sam",
    "Company": "",
    "Address": "561 Island Dr",
    "HouseNumber": null,
    "StreetName": null,
    "StreetSuffix": null,
    "PreDirect": null,
    "PostDirect": null,
    "AptNumber": null,
    "AptUnit": "",
    "UnitType": null,
    "District": null,
    "City": "Palm Beach",
    "CityCode": null,
    "State": "FL",
    "ZipCode": "33480",
    "ZipCode4": null,
    "DPVCode": null,
    "SuiteStatus": null,
    "DeliveryPointCheckDigit": null,
    "DPVFootnotes": null,
    "DeliveryPointCode": null,
    "CountyFips": null,
    "Msa": null,
    "PakHash": null,
    "ParsedAddressKey": null,
    "StandardizationError": null,
    "StandardizationResult": null,
    "Latitude": null,
    "Longitude": null,
    "CensusBlock": null,
    "CensusTract": null,
    "GeoCoderResult": null,
    "CarrierRoute": null,
    "Country": "",
    "CountryCode": "US",
    "PhoneAC": null,
    "PhoneEX": null,
    "PhoneEXT": null,
    "Phone": "9999999999",
    "Route": null,
    "Title": null
  },
  "PaymentTypeId": 1,
  "CreditCard": {
    "Type": "VISA",
    "Number": "411111******1111",
    "NumberFirstTwoDigits": "",
    "NumberLastFourDigits": "4111",
    "ExpirationMonth": "12",
    "ExpirationYear": "23",
    "SecurityCode": null,
    "OwnerName": "Neetha12 Sam112"
  },
  "BankAccount": null,
  "PayPalInfo": null,
  "iTunesInfo": null,
  "ApplePayInfo": null,
  "GooglePlayInfo": null,
  "AmazonInfo": null,
  "ActivateEZPay": true,
  "Amount": {
    "AmountCharged": 34.23,
    "ActivationFee": 0,
    "TaxAmount": 2.24,
    "SubscriptionCost": 31.99
  },
  "RecurringPaymentDayOfMonth": 0,
  "PaymentMethodId": "037641186",
  "CustomerId": null,
  "StartDate": null,
  "ExpirationDate": "1970-01-01T01:01:01",
  "ValidateAddress": false,
  "IgnoreRoutableErrors": true,
  "IgnoreExistingSubscriberCheck": false,
  "OptInForEedition": false,
  "OptInPreviousSunday": false,
  "OptOutOfDigitalContent": false,
  "UserId": -1,
  "StartType": "NewStart",
  "TrialPeriodDays": 0,
  "PassPeriodDays": 0,
  "PassCode": "",
  "SubscriptionId": 0,
  "Products": [
    {
      "ExternalProductId": "100079",
      "MerchantProductId": null,
      "ProductQuantity": 1,
      "ProductId": 0
    }
  ],
  "SalesPerson": null,
  "ParentEventId": null,
  "OfferCode": null,
  "LegacyAccountNumber": null,
  "PresentationName": "Default",
  "CouponCode": null,
  "StartReason": "",
  "TransactionId": null,
  "AuthorizationCode": null,
  "OrderId": null,
  "LocationName": null,
  "LocationId": null,
  "InitialCredit": null,
  "EbillEmail": null,
  "SalesTeamId": 0,
  "SourceCode": null,
  "BillingSubscriber": null,
  "IsDigital": false,
  "ApplePayPayload": null,
  "SendEmail": null,
  "OneTimeUseCode": null
}'
```

### Response example

The following is a json example response from the `/Subscriptions` endpoint:

```json
 {
    "SubscriptionID": 444979,
    "SubscriberID": 433515,
    "EventId": 10786,
    "AccountNumber": "3796617",
    "PaymentAuthorizationCode": "888888",
    "RedirectUrl": null
}
```

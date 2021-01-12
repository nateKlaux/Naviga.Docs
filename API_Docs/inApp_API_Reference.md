
## Get user by email

> **GET** `api/User/{type}?email={email}`

<!-- Delete this comment after the method and syntax above have been replaced with yours. -->

### Description

This end point does ............ 

<!-- Enter a few sentences of description. (What is it for, and what can it do?) -->

### Parameters

Parameter Type | Parameter | Value | Required | Description
-------------- | --------- | ----- | -------- | ----------
HEAD | Authorization | String | Y |  Endpoint's authorization.
HEAD | X-SourceSystem  | String | Y |  
HEAD | X-MediaGroupCode | String | Y | 
HEAD | X-ClientCode | String | Y | 
HEAD | X-PaperCode | String | Y | 
QUERY_STRING | email | String | Y | Unique identifer of the User in Naviga's system.
URL_PARAM | Type | Number | Y | Defines where to look for the user. `1` = User Provider; `2` = Naviga's database; `0` User provider and Naviga's database (recommended)

### Examples

#### Request

```HTTP
HTTP REQUEST EXAMPLE HERE

```

#### Response

The following is a JSON example of a successful response from the `api/User/{type}?email={email}` endpoint:

```JSON
Response will be an object containing the user information 

{ 

  "Code": 0, 

  "Errors": [ 

    { 

      "Message": "string", 

      "Code": "string", 

      "Type": { 

        "Id": 0, 

        "Code": "string" 

      }, 

      "ErrorSource": "string" 

    } 

  ], 

  "Result": { 

    "User": { 

      "RegistrationId": 0, 

      "LoginName": "string", 

      "LoginPassword": "string", 

      "IsActive": 0, 

      "CustomerRegistrationId": "string", 

      "EncryptedCustomerRegistrationId": "string", 

      "FirstName": "string", 

      "LastName": "string", 

      "Email": "string", 

      "Gender": "string", 

      "PhoneAc": "string", 

      "PhoneEx": "string", 

      "PhoneExt": "string", 

      "Phone": "string", 

      "MobilePhone": "string", 

      "OptInEVantageSubscriberRewards": true, 

      "OptInSpecialOffers": true, 

      "OptInContestAndPromotions": true, 

      "OptInPaperlessBilling": true, 

      "OptInEEdition": true, 

      "OptInEEditionEmailNotification": true, 

      "OptInSubscriberDiscounts": true, 

      "OptInAdvertiserEmails": true, 

      "MemberEvent": true, 

      "ContentEngagement": true, 

      "SUBCOM": true, 

      "Survey": true, 

      "AccountUpdates": true, 

      "DateOfBirth": "string", 

      "BirthYear": "string", 

      "AcceptsEmailOffers": 0, 

      "AcceptsEmailAds": 0, 

      "AcceptsEmailPromotions": 0, 

      "IsOkToEmail": 0, 

      "IsOkToPhone": 0, 

      "IsOkToMail": 0, 

      "AcceptsEENotification": 0, 

      "ChangeDate": "2018-07-24T11:20:15.403Z", 

      "DateRegistered": "2018-07-24T11:20:15.403Z", 

      "IsSocial": true, 

      "DisplayName": "string", 

      "AgreeToTerms": true, 

      "OptOutMarketing": true, 

      "Photo": "string" 

    } 

  } 

} 

```

### Response Codes

Naviga's API attempts to return appropriate HTTP status codes for every request.

| Status Code | Response                                                    |
|-------------|-------------------------------------------------------------|
| 400         | `{"error":"Authorization is missing."}`                     |
| 400         | `{"error":"X-SourceSystem is missing."}`                    |
| 400         | `{"error":"request cannot be null."}`                       |
| 401         | `{"error":"Invalid Authorization."}`                        |
| 401         | `{"error":"Invalid X-SourceSystem."}`                       |
| 500         | `{"error":"Something went wrong. Please try again later."}` |

## Create a user

> **POST** `api/User`

### Description

This endpoint does............

<!-- Enter a few sentences of description. (What is it for, and what can it do?) -->

### Parameters

Parameter Type | Parameter | Value | Required | Description
-------------- | --------- | ----- | -------- | ----------
| HEAD | Authorization | string | Y |  |
| HEAD | X-SourceSystem | string | Y |  |
| HEAD | X-MediaGroupCode | string | Y |  |
| HEAD | X-ClientCode | string | Y |  |
| HEAD | X-PaperCode | string | Y |  |
| BODY | Email | string | Y |  |
| BODY | Password | string | N |  |
| BODY | CreationMode | number | Y | Defines where to create the user. `1` = User provider; `2` = Naviga's database; `0` = both (_highly recommended_) |
| BODY | CustomerRegistrationId | string | N |  |
| BODY | FirstName | string | N |  |
| BODY | LastName | string | N |  |
| BODY | PhonaAc | string | N |  |
| BODY | PhoneEx | string | N |  |
| BODY | PhoneExt | string | N |  |
| BODY | MobilePhone | string | N |  |
| BODY | DOB | string | N |  |
| BODY | BirthYear | string | N |  |
| BODY | Gender | string | N |  |
| BODY | OptInEVantageSubscriberRewards | boolean | N |  |
| BODY | OptInSpecialOffers | boolean | N |  |
| BODY | OptInContestAndPromotions | boolean | N |  |
| BODY | OptInPaperlessBilling | boolean | N |  |
| BODY | OptInEEdition | boolean | N |  |
| BODY | OptInEEditionEmailNtification | boolean | N |  |
| BODY | OptInSubscriberDiscounts | boolean | N |  |
| BODY | OptInAdvertiserEmails | boolean | N |  |
| BODY | MemberEvent | boolean | N |  |
| BODY | ContentEngagement | boolean | N |  |
| BODY | SUBCOM | boolean | N |  |
| BODY | Survey | boolean | N |  |
| BODY | AccountUpdates | boolean | N | 0-255 |
| BODY | AcceptsEmailOffers | number | N | 0-255 |
| BODY | AcceptsEmailAds | number | N | 0-255 |
| BODY | AcceptsEmailPromotions | number | N | 0-255 |
| BODY | IsOkToEmail | number | N | 0-255 |
| BODY | IsOkToPhone | number | N | 0-255 |
| BODY | IsOkToMail | number | N | 0-255 |
| BODY | AcceptsEENtification | number | N |  |
| BODY | AcceptsTermsOfService | boolean | N |  |
| BODY | Photo | string | N |  |
| BODY | OptOutMarketing | boolean | N |  |

### Examples

#### Request

```HTTP
HTTP REQUEST EXAMPLE HERE

```

#### Response

The following is a JSON example of a successful response from the `api/User` endpoint:

```JSON
{ 

  "Code": 0, 

  "Errors": [ 

    { 

      "Message": "string", 

      "Code": "string", 

      "Type": { 

        "Id": 0, 

        "Code": "string" 

      }, 

      "ErrorSource": "string" 

    } 

  ], 

  "Result": { 

    "CustomerRegistrationId": "string", 

    "EncryptedCustomerRegistrationId": "string", 

    "Mg2RegistrationId": 0 

  } 

} 
```

### Response Codes

Naviga's API attempts to return appropriate HTTP status codes for every request.

| Status Code | Response                                                    |
|-------------|-------------------------------------------------------------|
| 400         | `{"error":"Authorization is missing."}`                     |
| 400         | `{"error":"X-SourceSystem is missing."}`                    |
| 400         | `{"error":"request cannot be null."}`                       |
| 401         | `{"error":"Invalid Authorization."}`                        |
| 401         | `{"error":"Invalid X-SourceSystem."}`                       |
| 500         | `{"error":"Something went wrong. Please try again later."}` |


## Get Subscriptions by Customer Registration Id

> **GET** `/users/12345/subscriptions/?CustomerRegistrationId=12345&paperCodesAllowed=JCO,JCOE`

### Description

This endpoint gets the active subscriptions of a customer.

<!-- Enter a few sentences of description. (What is it for, and what can it do?) -->

### Parameters

Parameter Type | Parameter | Value | Required | Description
-------------- | --------- | ----- | -------- | ----------
| HEAD | Authorization | string | Y |  |
| HEAD | X-SourceSystem | string | Y |  |
| HEAD | X-MediaGroupCode | string | Y |  |
| HEAD | X-ClientCode | string | Y |  |
| HEAD | X-PaperCode | string | Y |  |
| URL_PARAM | customerRegistrationId  | string | Y | The unique identifier of a customer in Naviga. Also known as `Customer Registration Id`. Represents an user. |
| URL_PARAM | paperCodesAllowed  | string | N | Set of paper codes allowed for the subscription's lookup. |
| URL_PARAM | includeStoppedSubscriptions | boolean | N | Determines whether the response includes stopped subscriptions. |

### Examples

#### Request

```HTTP
HTTP REQUEST EXAMPLE HERE

```

#### Response

The following is a JSON example of a successful response from the `/users/12345/subscriptions/?CustomerRegistrationId=12345&paperCodesAllowed=JCO,JCOE` endpoint:

```JSON

An example response is:
{
  "Code": 0,
  "Errors": [
    {
      "Message": "string",
      "Code": "string",
      "Type": {
        "Id": 0,
        "Code": "string"
      }
    }
  ],
  "Result": {
    "OwnedSubscriptions": [
      {
        "SubscriptionId": 0,
        "ExternalSubscriptionId": "string",
        "SubscriberId": 0,
        "ExternalSubscriberId": "string",
        "AccountNumber": "string",
        "FirstName": "string",
        "LastName": "string",
        "Email": "string",
        "BillingPlanId": 0,
        "OfferId": 0,
        "PromotionId": 0,
        "PremiumGiftId": 0,
        "Phone": "string",
        "CompanyName": "string",
        "ExternalSubscriptionBillingPlanId": "string",
        "PaymentMethodId": 0,
        "ExternalSubscriptionPaymentMethodId": "string",
        "PaymentMethod": {
          "PaymentMethodId": 0,
          "ExternalPaymentMethodId": "string",
          "HolderName": "string",
          "Active": true,
          "PaymentMethodType": "iTunes",
          "FirstName": "string",
          "LastName": "string",
          "CompanyName": "string",
          "Phone": "string",
          "BillingAddress": {
            "AddressId": 0,
            "ExternalAddressId": "string",
            "FullName": "string",
            "FirstName": "string",
            "LastName": "string",
            "Company": "string",
            "Address": "string",
            "HouseNumber": "string",
            "StreetName": "string",
            "StreetSuffix": "string",
            "PreDirect": "string",
            "PostDirect": "string",
            "AptNumber": "string",
            "AptUnit": "string",
            "UnitType": "string",
            "District": "string",
            "City": "string",
            "CityCode": "string",
            "State": "string",
            "ZipCode": "string",
            "ZipCode4": "string",
            "DPVCode": "string",
            "SuiteStatus": "string",
            "DeliveryPointCheckDigit": "string",
            "DPVFootnotes": "string",
            "DeliveryPointCode": "string",
            "CountyFips": "string",
            "Msa": "string",
            "ParsedAddressKey": "string",
            "StandardizationError": "string",
            "PakHash": "string",
            "StandardizationResult": "string",
            "Latitude": "string",
            "Longitude": "string",
            "CensusBlock": "string",
            "CensusTract": "string",
            "GeoCoderResult": "string",
            "CarrierRoute": "string",
            "Country": "string",
            "CountryCode": "string",
            "PhoneAC": "string",
            "PhoneEX": "string",
            "PhoneEXT": "string",
            "Phone": "string",
            "Route": "string",
            "Title": "string"
          }
        },
        "DeliveryAddress": {
          "AddressId": 0,
          "ExternalAddressId": "string",
          "FullName": "string",
          "FirstName": "string",
          "LastName": "string",
          "Company": "string",
          "Address": "string",
          "HouseNumber": "string",
          "StreetName": "string",
          "StreetSuffix": "string",
          "PreDirect": "string",
          "PostDirect": "string",
          "AptNumber": "string",
          "AptUnit": "string",
          "UnitType": "string",
          "District": "string",
          "City": "string",
          "CityCode": "string",
          "State": "string",
          "ZipCode": "string",
          "ZipCode4": "string",
          "DPVCode": "string",
          "SuiteStatus": "string",
          "DeliveryPointCheckDigit": "string",
          "DPVFootnotes": "string",
          "DeliveryPointCode": "string",
          "CountyFips": "string",
          "Msa": "string",
          "ParsedAddressKey": "string",
          "StandardizationError": "string",
          "PakHash": "string",
          "StandardizationResult": "string",
          "Latitude": "string",
          "Longitude": "string",
          "CensusBlock": "string",
          "CensusTract": "string",
          "GeoCoderResult": "string",
          "CarrierRoute": "string",
          "Country": "string",
          "CountryCode": "string",
          "PhoneAC": "string",
          "PhoneEX": "string",
          "PhoneEXT": "string",
          "Phone": "string",
          "Route": "string",
          "Title": "string"
        },
        "BillingAddress": {
          "AddressId": 0,
          "ExternalAddressId": "string",
          "FullName": "string",
          "FirstName": "string",
          "LastName": "string",
          "Company": "string",
          "Address": "string",
          "HouseNumber": "string",
          "StreetName": "string",
          "StreetSuffix": "string",
          "PreDirect": "string",
          "PostDirect": "string",
          "AptNumber": "string",
          "AptUnit": "string",
          "UnitType": "string",
          "District": "string",
          "City": "string",
          "CityCode": "string",
          "State": "string",
          "ZipCode": "string",
          "ZipCode4": "string",
          "DPVCode": "string",
          "SuiteStatus": "string",
          "DeliveryPointCheckDigit": "string",
          "DPVFootnotes": "string",
          "DeliveryPointCode": "string",
          "CountyFips": "string",
          "Msa": "string",
          "ParsedAddressKey": "string",
          "StandardizationError": "string",
          "PakHash": "string",
          "StandardizationResult": "string",
          "Latitude": "string",
          "Longitude": "string",
          "CensusBlock": "string",
          "CensusTract": "string",
          "GeoCoderResult": "string",
          "CarrierRoute": "string",
          "Country": "string",
          "CountryCode": "string",
          "PhoneAC": "string",
          "PhoneEX": "string",
          "PhoneEXT": "string",
          "Phone": "string",
          "Route": "string",
          "Title": "string"
        },
        "MerchantId": "string",
        "Active": true,
        "HasPrintProducts": true,
        "HasDigitalProducts": true,
        "Status": "string",
        "StatusDescription": "string",
        "StartDate": "2016-07-27T13:47:49.352Z",
        "ExpirationDate": "2016-07-27T13:47:49.352Z",
        "NewspaperId": 0,
        "NewspaperName": "string",
        "PaperCode": "string",
        "Products": [
          {
            "SubscriptionProductId": 0,
            "ExternalSubscriptionProductId": "string",
            "SubscriptionId": 0,
            "ProductId": 0,
            "Product": {
              "ProductId": 0,
              "ExternalProductId": "string",
              "ExternalMerchantId": "string",
              "Name": "string",
              "Description": "string",
              "Price": 0,
              "Currency": "string",
              "Active": true,
              "PaperCode": "string",
              "NewspaperId": 0,
              "ServiceTypeId": 0,
              "IsPrint": true,
              "IsDigital": true,
              "ServiceType": {
                "ServiceTypeId": 0,
                "Name": "string",
                "Description": "string",
                "Sequence": 0,
                "Days": 0,
                "Code": "string",
                "Active": true,
                "eEditionAccess": true,
                "ServiceDays": [
                  {
                    "Day": 0,
                    "DayName": "string",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  }
                ]
              },
              "Discount": "string",
              "IsAddOn": true,
              "DeliveryMethod": "string",
              "OneTimeCharge": true,
              "RegularRate": 0
            },
            "Amount": 0,
            "Currency": "string",
            "CampaignId": "string",
            "CampaignCode": "string",
            "IsAutoRenewal": true,
            "Cycles": 0,
            "Copies": "string",
            "RemainingCycles": 0
          }
        ],
        "NewStartQueueId": 0,
        "CirculationSystemAccountId": "string",
        "DateCreated": "2016-07-27T13:47:49.354Z",
        "ProcessingStatus": "string",
        "TransactionType": "string",
        "RateCode": "string",
        "HouseholdSubscriptionLevel": 0,
        "UpgradeSmartOfferSegment": "string",
        "DowngradeSmartOfferSegment": "string",
        "SubscriptionType": "string",
        "Sub3Code": "string",
        "PromoCert": "string",
        "PromoCredit": "string",
        "PromoSource": "string",
        "PromoSubSource": "string",
        "StartSource": "string",
        "StartReason": "string",
        "StopSource": "string",
        "StopReason": "string",
        "IsEZPay": true,
        "HaseBill": true,
        "IsTerm": true,
        "IsTrial": true,
        "PaymentFlag": "string",
        "DailyRate": 0,
        "DeliveryMethod": "string",
        "WeekDayCredit": 0,
        "SundayCredit": 0,
        "IsCompSubscription": true,
        "IsMailSubscription": true,
        "DailyRateWithTaxes": 0,
        "UpgradeSubscriptionPromotionId": 0,
        "DowngradeSubscriptionPromotionId": 0,
        "UpgradeProductsPromotionId": 0,
        "SubscriptionDescription": "string",
        "BaseProduct": {
          "ProductId": 0,
          "ExternalProductId": "string",
          "ExternalMerchantId": "string",
          "Name": "string",
          "Description": "string",
          "Price": 0,
          "Currency": "string",
          "Active": true,
          "PaperCode": "string",
          "NewspaperId": 0,
          "ServiceTypeId": 0,
          "IsPrint": true,
          "IsDigital": true,
          "ServiceType": {
            "ServiceTypeId": 0,
            "Name": "string",
            "Description": "string",
            "Sequence": 0,
            "Days": 0,
            "Code": "string",
            "Active": true,
            "eEditionAccess": true,
            "ServiceDays": [
              {
                "Day": 0,
                "DayName": "string",
                "PrintAllowed": true,
                "DigitalAllowed": true
              }
            ]
          },
          "Discount": "string",
          "IsAddOn": true,
          "DeliveryMethod": "string",
          "OneTimeCharge": true,
          "RegularRate": 0
        }
      },
      "DeliveryStartDate": "2016-08-15T14:46:05.965Z",
      "EffectiveStartDate": "2016-08-15T14:46:05.965Z",
      "PermanentStopDate": "2016-08-15T14:46:05.965Z"
    ],
    "GuestSubscriptions": [
      {
        "SubscriptionId": 0,
        "ExternalSubscriptionId": "string",
        "SubscriberId": 0,
        "ExternalSubscriberId": "string",
        "AccountNumber": "string",
        "FirstName": "string",
        "LastName": "string",
        "Email": "string",
        "BillingPlanId": 0,
        "OfferId": 0,
        "PromotionId": 0,
        "PremiumGiftId": 0,
        "Phone": "string",
        "CompanyName": "string",
        "ExternalSubscriptionBillingPlanId": "string",
        "PaymentMethodId": 0,
        "ExternalSubscriptionPaymentMethodId": "string",
        "PaymentMethod": {
          "PaymentMethodId": 0,
          "ExternalPaymentMethodId": "string",
          "HolderName": "string",
          "Active": true,
          "PaymentMethodType": "GooglePlay",
          "FirstName": "string",
          "LastName": "string",
          "CompanyName": "string",
          "Phone": "string",
          "BillingAddress": {
            "AddressId": 0,
            "ExternalAddressId": "string",
            "FullName": "string",
            "FirstName": "string",
            "LastName": "string",
            "Company": "string",
            "Address": "string",
            "HouseNumber": "string",
            "StreetName": "string",
            "StreetSuffix": "string",
            "PreDirect": "string",
            "PostDirect": "string",
            "AptNumber": "string",
            "AptUnit": "string",
            "UnitType": "string",
            "District": "string",
            "City": "string",
            "CityCode": "string",
            "State": "string",
            "ZipCode": "string",
            "ZipCode4": "string",
            "DPVCode": "string",
            "SuiteStatus": "string",
            "DeliveryPointCheckDigit": "string",
            "DPVFootnotes": "string",
            "DeliveryPointCode": "string",
            "CountyFips": "string",
            "Msa": "string",
            "ParsedAddressKey": "string",
            "StandardizationError": "string",
            "PakHash": "string",
            "StandardizationResult": "string",
            "Latitude": "string",
            "Longitude": "string",
            "CensusBlock": "string",
            "CensusTract": "string",
            "GeoCoderResult": "string",
            "CarrierRoute": "string",
            "Country": "string",
            "CountryCode": "string",
            "PhoneAC": "string",
            "PhoneEX": "string",
            "PhoneEXT": "string",
            "Phone": "string",
            "Route": "string",
            "Title": "string"
          }
        },
        "DeliveryAddress": {
          "AddressId": 0,
          "ExternalAddressId": "string",
          "FullName": "string",
          "FirstName": "string",
          "LastName": "string",
          "Company": "string",
          "Address": "string",
          "HouseNumber": "string",
          "StreetName": "string",
          "StreetSuffix": "string",
          "PreDirect": "string",
          "PostDirect": "string",
          "AptNumber": "string",
          "AptUnit": "string",
          "UnitType": "string",
          "District": "string",
          "City": "string",
          "CityCode": "string",
          "State": "string",
          "ZipCode": "string",
          "ZipCode4": "string",
          "DPVCode": "string",
          "SuiteStatus": "string",
          "DeliveryPointCheckDigit": "string",
          "DPVFootnotes": "string",
          "DeliveryPointCode": "string",
          "CountyFips": "string",
          "Msa": "string",
          "ParsedAddressKey": "string",
          "StandardizationError": "string",
          "PakHash": "string",
          "StandardizationResult": "string",
          "Latitude": "string",
          "Longitude": "string",
          "CensusBlock": "string",
          "CensusTract": "string",
          "GeoCoderResult": "string",
          "CarrierRoute": "string",
          "Country": "string",
          "CountryCode": "string",
          "PhoneAC": "string",
          "PhoneEX": "string",
          "PhoneEXT": "string",
          "Phone": "string",
          "Route": "string",
          "Title": "string"
        },
        "BillingAddress": {
          "AddressId": 0,
          "ExternalAddressId": "string",
          "FullName": "string",
          "FirstName": "string",
          "LastName": "string",
          "Company": "string",
          "Address": "string",
          "HouseNumber": "string",
          "StreetName": "string",
          "StreetSuffix": "string",
          "PreDirect": "string",
          "PostDirect": "string",
          "AptNumber": "string",
          "AptUnit": "string",
          "UnitType": "string",
          "District": "string",
          "City": "string",
          "CityCode": "string",
          "State": "string",
          "ZipCode": "string",
          "ZipCode4": "string",
          "DPVCode": "string",
          "SuiteStatus": "string",
          "DeliveryPointCheckDigit": "string",
          "DPVFootnotes": "string",
          "DeliveryPointCode": "string",
          "CountyFips": "string",
          "Msa": "string",
          "ParsedAddressKey": "string",
          "StandardizationError": "string",
          "PakHash": "string",
          "StandardizationResult": "string",
          "Latitude": "string",
          "Longitude": "string",
          "CensusBlock": "string",
          "CensusTract": "string",
          "GeoCoderResult": "string",
          "CarrierRoute": "string",
          "Country": "string",
          "CountryCode": "string",
          "PhoneAC": "string",
          "PhoneEX": "string",
          "PhoneEXT": "string",
          "Phone": "string",
          "Route": "string",
          "Title": "string"
        },
        "MerchantId": "string",
        "Active": true,
        "HasPrintProducts": true,
        "HasDigitalProducts": true,
        "Status": "string",
        "StatusDescription": "string",
        "StartDate": "2016-07-27T13:47:49.356Z",
        "ExpirationDate": "2016-07-27T13:47:49.356Z",
        "NewspaperId": 0,
        "NewspaperName": "string",
        "PaperCode": "string",
        "Products": [
          {
            "SubscriptionProductId": 0,
            "ExternalSubscriptionProductId": "string",
            "SubscriptionId": 0,
            "ProductId": 0,
            "Product": {
              "ProductId": 0,
              "ExternalProductId": "string",
              "ExternalMerchantId": "string",
              "Name": "string",
              "Description": "string",
              "Price": 0,
              "Currency": "string",
              "Active": true,
              "PaperCode": "string",
              "NewspaperId": 0,
              "ServiceTypeId": 0,
              "IsPrint": true,
              "IsDigital": true,
              "ServiceType": {
                "ServiceTypeId": 0,
                "Name": "string",
                "Description": "string",
                "Sequence": 0,
                "Days": 0,
                "Code": "string",
                "Active": true,
                "eEditionAccess": true,
                "ServiceDays": [
                  {
                    "Day": 0,
                    "DayName": "string",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  }
                ]
              },
              "Discount": "string",
              "IsAddOn": true,
              "DeliveryMethod": "string",
              "OneTimeCharge": true,
              "RegularRate": 0
            },
            "Amount": 0,
            "Currency": "string",
            "CampaignId": "string",
            "CampaignCode": "string",
            "IsAutoRenewal": true,
            "Cycles": 0,
            "Copies": "string",
            "RemainingCycles": 0
          }
        ],
        "NewStartQueueId": 0,
        "CirculationSystemAccountId": "string",
        "DateCreated": "2016-07-27T13:47:49.357Z",
        "ProcessingStatus": "string",
        "TransactionType": "string",
        "RateCode": "string",
        "HouseholdSubscriptionLevel": 0,
        "UpgradeSmartOfferSegment": "string",
        "DowngradeSmartOfferSegment": "string",
        "SubscriptionType": "string",
        "Sub3Code": "string",
        "PromoCert": "string",
        "PromoCredit": "string",
        "PromoSource": "string",
        "PromoSubSource": "string",
        "StartSource": "string",
        "StartReason": "string",
        "StopSource": "string",
        "StopReason": "string",
        "IsEZPay": true,
        "HaseBill": true,
        "IsTerm": true,
        "IsTrial": true,
        "PaymentFlag": "string",
        "DailyRate": 0,
        "DeliveryMethod": "string",
        "WeekDayCredit": 0,
        "SundayCredit": 0,
        "IsCompSubscription": true,
        "IsMailSubscription": true,
        "DailyRateWithTaxes": 0,
        "UpgradeSubscriptionPromotionId": 0,
        "DowngradeSubscriptionPromotionId": 0,
        "UpgradeProductsPromotionId": 0,
        "SubscriptionDescription": "string",
        "BaseProduct": {
          "ProductId": 0,
          "ExternalProductId": "string",
          "ExternalMerchantId": "string",
          "Name": "string",
          "Description": "string",
          "Price": 0,
          "Currency": "string",
          "Active": true,
          "PaperCode": "string",
          "NewspaperId": 0,
          "ServiceTypeId": 0,
          "IsPrint": true,
          "IsDigital": true,
          "ServiceType": {
            "ServiceTypeId": 0,
            "Name": "string",
            "Description": "string",
            "Sequence": 0,
            "Days": 0,
            "Code": "string",
            "Active": true,
            "eEditionAccess": true,
            "ServiceDays": [
              {
                "Day": 0,
                "DayName": "string",
                "PrintAllowed": true,
                "DigitalAllowed": true
              }
            ]
          },
          "Discount": "string",
          "IsAddOn": true,
          "DeliveryMethod": "string",
          "OneTimeCharge": true,
          "RegularRate": 0
        }
      },
      "DeliveryStartDate": "2016-08-15T14:46:05.965Z",
      "EffectiveStartDate": "2016-08-15T14:46:05.965Z",
      "PermanentStopDate": "2016-08-15T14:46:05.965Z"
    ],
    "InactiveGuestSubscriptions": [
      {
        "SubscriptionId": 0,
        "ExternalSubscriptionId": "string",
        "SubscriberId": 0,
        "ExternalSubscriberId": "string",
        "AccountNumber": "string",
        "FirstName": "string",
        "LastName": "string",
        "Email": "string",
        "BillingPlanId": 0,
        "OfferId": 0,
        "PromotionId": 0,
        "PremiumGiftId": 0,
        "Phone": "string",
        "CompanyName": "string",
        "ExternalSubscriptionBillingPlanId": "string",
        "PaymentMethodId": 0,
        "ExternalSubscriptionPaymentMethodId": "string",
        "PaymentMethod": {
          "PaymentMethodId": 0,
          "ExternalPaymentMethodId": "string",
          "HolderName": "string",
          "Active": true,
          "PaymentMethodType": "CreditCard",
          "FirstName": "string",
          "LastName": "string",
          "CompanyName": "string",
          "Phone": "string",
          "BillingAddress": {
            "AddressId": 0,
            "ExternalAddressId": "string",
            "FullName": "string",
            "FirstName": "string",
            "LastName": "string",
            "Company": "string",
            "Address": "string",
            "HouseNumber": "string",
            "StreetName": "string",
            "StreetSuffix": "string",
            "PreDirect": "string",
            "PostDirect": "string",
            "AptNumber": "string",
            "AptUnit": "string",
            "UnitType": "string",
            "District": "string",
            "City": "string",
            "CityCode": "string",
            "State": "string",
            "ZipCode": "string",
            "ZipCode4": "string",
            "DPVCode": "string",
            "SuiteStatus": "string",
            "DeliveryPointCheckDigit": "string",
            "DPVFootnotes": "string",
            "DeliveryPointCode": "string",
            "CountyFips": "string",
            "Msa": "string",
            "ParsedAddressKey": "string",
            "StandardizationError": "string",
            "PakHash": "string",
            "StandardizationResult": "string",
            "Latitude": "string",
            "Longitude": "string",
            "CensusBlock": "string",
            "CensusTract": "string",
            "GeoCoderResult": "string",
            "CarrierRoute": "string",
            "Country": "string",
            "CountryCode": "string",
            "PhoneAC": "string",
            "PhoneEX": "string",
            "PhoneEXT": "string",
            "Phone": "string",
            "Route": "string",
            "Title": "string"
          }
        },
        "DeliveryAddress": {
          "AddressId": 0,
          "ExternalAddressId": "string",
          "FullName": "string",
          "FirstName": "string",
          "LastName": "string",
          "Company": "string",
          "Address": "string",
          "HouseNumber": "string",
          "StreetName": "string",
          "StreetSuffix": "string",
          "PreDirect": "string",
          "PostDirect": "string",
          "AptNumber": "string",
          "AptUnit": "string",
          "UnitType": "string",
          "District": "string",
          "City": "string",
          "CityCode": "string",
          "State": "string",
          "ZipCode": "string",
          "ZipCode4": "string",
          "DPVCode": "string",
          "SuiteStatus": "string",
          "DeliveryPointCheckDigit": "string",
          "DPVFootnotes": "string",
          "DeliveryPointCode": "string",
          "CountyFips": "string",
          "Msa": "string",
          "ParsedAddressKey": "string",
          "StandardizationError": "string",
          "PakHash": "string",
          "StandardizationResult": "string",
          "Latitude": "string",
          "Longitude": "string",
          "CensusBlock": "string",
          "CensusTract": "string",
          "GeoCoderResult": "string",
          "CarrierRoute": "string",
          "Country": "string",
          "CountryCode": "string",
          "PhoneAC": "string",
          "PhoneEX": "string",
          "PhoneEXT": "string",
          "Phone": "string",
          "Route": "string",
          "Title": "string"
        },
        "BillingAddress": {
          "AddressId": 0,
          "ExternalAddressId": "string",
          "FullName": "string",
          "FirstName": "string",
          "LastName": "string",
          "Company": "string",
          "Address": "string",
          "HouseNumber": "string",
          "StreetName": "string",
          "StreetSuffix": "string",
          "PreDirect": "string",
          "PostDirect": "string",
          "AptNumber": "string",
          "AptUnit": "string",
          "UnitType": "string",
          "District": "string",
          "City": "string",
          "CityCode": "string",
          "State": "string",
          "ZipCode": "string",
          "ZipCode4": "string",
          "DPVCode": "string",
          "SuiteStatus": "string",
          "DeliveryPointCheckDigit": "string",
          "DPVFootnotes": "string",
          "DeliveryPointCode": "string",
          "CountyFips": "string",
          "Msa": "string",
          "ParsedAddressKey": "string",
          "StandardizationError": "string",
          "PakHash": "string",
          "StandardizationResult": "string",
          "Latitude": "string",
          "Longitude": "string",
          "CensusBlock": "string",
          "CensusTract": "string",
          "GeoCoderResult": "string",
          "CarrierRoute": "string",
          "Country": "string",
          "CountryCode": "string",
          "PhoneAC": "string",
          "PhoneEX": "string",
          "PhoneEXT": "string",
          "Phone": "string",
          "Route": "string",
          "Title": "string"
        },
        "MerchantId": "string",
        "Active": true,
        "HasPrintProducts": true,
        "HasDigitalProducts": true,
        "Status": "string",
        "StatusDescription": "string",
        "StartDate": "2016-07-27T13:47:49.358Z",
        "ExpirationDate": "2016-07-27T13:47:49.358Z",
        "NewspaperId": 0,
        "NewspaperName": "string",
        "PaperCode": "string",
        "Products": [
          {
            "SubscriptionProductId": 0,
            "ExternalSubscriptionProductId": "string",
            "SubscriptionId": 0,
            "ProductId": 0,
            "Product": {
              "ProductId": 0,
              "ExternalProductId": "string",
              "ExternalMerchantId": "string",
              "Name": "string",
              "Description": "string",
              "Price": 0,
              "Currency": "string",
              "Active": true,
              "PaperCode": "string",
              "NewspaperId": 0,
              "ServiceTypeId": 0,
              "IsPrint": true,
              "IsDigital": true,
              "ServiceType": {
                "ServiceTypeId": 0,
                "Name": "string",
                "Description": "string",
                "Sequence": 0,
                "Days": 0,
                "Code": "string",
                "Active": true,
                "eEditionAccess": true,
                "ServiceDays": [
                  {
                    "Day": 0,
                    "DayName": "string",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  }
                ]
              },
              "Discount": "string",
              "IsAddOn": true,
              "DeliveryMethod": "string",
              "OneTimeCharge": true,
              "RegularRate": 0
            },
            "Amount": 0,
            "Currency": "string",
            "CampaignId": "string",
            "CampaignCode": "string",
            "IsAutoRenewal": true,
            "Cycles": 0,
            "Copies": "string",
            "RemainingCycles": 0
          }
        ],
        "NewStartQueueId": 0,
        "CirculationSystemAccountId": "string",
        "DateCreated": "2016-07-27T13:47:49.358Z",
        "ProcessingStatus": "string",
        "TransactionType": "string",
        "RateCode": "string",
        "HouseholdSubscriptionLevel": 0,
        "UpgradeSmartOfferSegment": "string",
        "DowngradeSmartOfferSegment": "string",
        "SubscriptionType": "string",
        "Sub3Code": "string",
        "PromoCert": "string",
        "PromoCredit": "string",
        "PromoSource": "string",
        "PromoSubSource": "string",
        "StartSource": "string",
        "StartReason": "string",
        "StopSource": "string",
        "StopReason": "string",
        "IsEZPay": true,
        "HaseBill": true,
        "IsTerm": true,
        "IsTrial": true,
        "PaymentFlag": "string",
        "DailyRate": 0,
        "DeliveryMethod": "string",
        "WeekDayCredit": 0,
        "SundayCredit": 0,
        "IsCompSubscription": true,
        "IsMailSubscription": true,
        "DailyRateWithTaxes": 0,
        "UpgradeSubscriptionPromotionId": 0,
        "DowngradeSubscriptionPromotionId": 0,
        "UpgradeProductsPromotionId": 0,
        "SubscriptionDescription": "string",
        "BaseProduct": {
          "ProductId": 0,
          "ExternalProductId": "string",
          "ExternalMerchantId": "string",
          "Name": "string",
          "Description": "string",
          "Price": 0,
          "Currency": "string",
          "Active": true,
          "PaperCode": "string",
          "NewspaperId": 0,
          "ServiceTypeId": 0,
          "IsPrint": true,
          "IsDigital": true,
          "ServiceType": {
            "ServiceTypeId": 0,
            "Name": "string",
            "Description": "string",
            "Sequence": 0,
            "Days": 0,
            "Code": "string",
            "Active": true,
            "eEditionAccess": true,
            "ServiceDays": [
              {
                "Day": 0,
                "DayName": "string",
                "PrintAllowed": true,
                "DigitalAllowed": true
              }
            ]
          },
          "Discount": "string",
          "IsAddOn": true,
          "DeliveryMethod": "string",
          "OneTimeCharge": true,
          "RegularRate": 0
        }
      },
      "DeliveryStartDate": "2016-08-15T14:46:05.965Z",
      "EffectiveStartDate": "2016-08-15T14:46:05.965Z",
      "PermanentStopDate": "2016-08-15T14:46:05.965Z"
    ]
  }
}
```

### Response Codes

Naviga's API attempts to return appropriate HTTP status codes for every request.

| Status Code | Response                                                    |
|-------------|-------------------------------------------------------------|
| 400         | `{"error":"Authorization is missing."}`                     |
| 400         | `{"error":"X-SourceSystem is missing."}`                    |
| 400         | `{"error":"request cannot be null."}`                       |
| 401         | `{"error":"Invalid Authorization."}`                        |
| 401         | `{"error":"Invalid X-SourceSystem."}`                       |
| 500         | `{"error":"Something went wrong. Please try again later."}` |



## ENDPOITN NAME

> **POST** `...........`

### Description

This endpoint does............

<!-- Enter a few sentences of description. (What is it for, and what can it do?) -->

### Parameters

Parameter Type | Parameter | Value | Required | Description
-------------- | --------- | ----- | -------- | ----------
| HEAD | Authorization | string | Y |  |
| HEAD | X-SourceSystem | string | Y |  |
| HEAD | X-MediaGroupCode | string | Y |  |
| HEAD | X-ClientCode | string | Y |  |
| HEAD | X-PaperCode | string | Y |  |
| BODY | Email | string | Y |  |
| BODY | Password | string | N |  |

### Examples

#### Request

```HTTP
HTTP REQUEST EXAMPLE HERE

```

#### Response

The following is a JSON example of a successful response from the `......` endpoint:

```JSON

```

### Response Codes

Naviga's API attempts to return appropriate HTTP status codes for every request.

| Status Code | Response                                                    |
|-------------|-------------------------------------------------------------|
| 400         | `{"error":"Authorization is missing."}`                     |
| 400         | `{"error":"X-SourceSystem is missing."}`                    |
| 400         | `{"error":"request cannot be null."}`                       |
| 401         | `{"error":"Invalid Authorization."}`                        |
| 401         | `{"error":"Invalid X-SourceSystem."}`                       |
| 500         | `{"error":"Something went wrong. Please try again later."}` |
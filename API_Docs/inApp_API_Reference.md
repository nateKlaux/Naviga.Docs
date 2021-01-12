
## Standard flow  

This is the standard flow that our clients usually implement in their Apps.

The Store knows if you already had bought a subscription in that Store.  

The `GET User` call returns the customer registration ID if a user with that email already exists. If a customer doesn’t, use the `CreateUser` endpoint.

There’s no need to validate if the email has a Naviga's subscription already – with unlimited digital access for instance - because we have to insert the InApp subscription anyway. In this last scenario, if the user cancels the Naviga's one in the future, the will still have digital access using the inApp subscription.  

The `GetUser` / `CreateUser` call can be done after purchasing in the Store, buit before the `CreateSubcription` call. 

The `GetsubscriptionsByCustomerRegistrationId` endpoint here for good measure.

## Get user by email

> **GET** `api/User/{type}?email={email}`


### Description

This endpoint gets users account by using the user's email address. 


### Parameters

Parameter Type | Parameter | Data Type | Required | Description
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

The following is a cURL request example for the endpoint.

```
curl -X GET 
--header 'Accept: application/json' 
--header 'X-MediaGroupCode: MG2GroupStripe' 
--header 'X-ClientCode: DTI' 
--header 'X-PaperCode: MAA' 
--header 'X-SourceSystem: <***> 
--header 'Authorization: bearer <***>' 
--header 'X-RequestId: 0' 
'https://test.subscriberconcierge.com/User/0?email=nathan%40testing.com'
```

#### Response

The following is a JSON example of a successful response from the `api/User/{type}?email={email}` endpoint:

```JSON
{ 
  "Code": 200,
  "Errors": [],
  "Result": {
    "User": {
      "RegistrationId": 2937,
      "LoginName": "nathan@testing.com",
      "LoginPassword": "$2a$11$gYF08yClTtrFeJNKg1Pvs.WZZOaAo2Z0MtrFCXYV9AVXKMTGGi4f.",
      "CustomerRegistrationId": "2937",
      "EncryptedCustomerRegistrationId": "c1Naxk2z4Xc=",
      "FirstName": "nathan",
      "LastName": "laux",
      "Email": "nathan@testing.com",
      "Gender": null,
      "PhoneAc": null,
      "PhoneEx": null,
      "PhoneExt": null,
      "Phone": "--",
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
      "AcceptsEmailOffers": 78,
      "AcceptsEmailAds": 78,
      "AcceptsEmailPromotions": 78,
      "IsOkToEmail": 78,
      "IsOkToPhone": 78,
      "IsOkToMail": 78,
      "AcceptsEENotification": 78,
      "ChangeDate": "2021-01-12T18:05:18.733",
      "DateRegistered": null,
      "Photos": null,
      "IsSocial": false,
      "DisplayName": "nathan637460715185780759",
      "AgreeToTerms": false,
      "OptOutMarketing": false,
      "Photo": null,
      "VerificationCode": "2CF772",
      "Verified": false,
      "AuthSystem": {
        "AuthSystemId": 1,
        "AuthSystemCode": "MG2",
        "AuthSystemName": "MG2"
      },
      "UserState": {
        "UserStateId": 2,
        "UserStateCode": "Unverified"
      },
      "BounceType": null
    }
  },
  "SessionId": "02f6cf6b-acb2-468f-bab2-d51249a5a70c",
  "RequestId": "0"
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

This endpoint creates a user.

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
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
| BODY | VerifyEmail | boolean | Y |  |


### Examples

#### Request

The following is a cURL request example for the endpoint.

```JSON
curl 
-X POST 
--header 'Content-Type: application/json' 
--header 'Accept: application/json' 
--header 'X-MediaGroupCode: MG2GroupStripe' 
--header 'X-ClientCode: DTI' 
--header 'X-PaperCode: MAA' 
--header 'X-SourceSystem: ***' 
--header 'Authorization: ***' 
--header 'X-RequestId: 0' 
-d '{
  "Email": "nathan@testing.com",
  "Password": "asd987asd",
  "CreationMode": 0,
  "FirstName": "nathan",
  "LastName": "laux",  
  "VerifyEmail": true
}'
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

> **GET** `/users/{12345}/subscriptions/?CustomerRegistrationId={1234}5&paperCodesAllowed=JCO,JCOE`

### Description

This endpoint gets the active subscriptions of a customer using the customer's registration ID.

### Parameters

Parameter Type | Parameter | Data Type | Required | Description
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

The following is a cURL request example of the endpoint.

```HTTP
curl -X GET 
--header 'Accept: application/json' 
--header 'X-MediaGroupCode: MG2GroupStripe' 
--header 'X-ClientCode: DTI' 
--header 'X-PaperCode: VCP' 
--header 'X-SourceSystem: ***' 
--header 'Authorization: ***' 
--header 'X-RequestId: 0' 
```

#### Response

The following is a JSON example of a successful response from the `/users/12345/subscriptions/?CustomerRegistrationId=12345&paperCodesAllowed=JCO,JCOE` endpoint:

```JSON

An example response is:
{
  "Code": 200,
  "Errors": [],
  "Result": {
    "OwnedSubscriptions": [
      {
        "SubscriptionId": 69518,
        "ExternalSubscriptionId": "104791",
        "SubscriberId": 28488,
        "ExternalSubscriberId": "104791",
        "MerchantSubscriberId": null,
        "AccountNumber": "104791",
        "FirstName": "STEVE & JILL",
        "LastName": "RAGEN",
        "FullName": "STEVE & JILL RAGEN",
        "Email": "",
        "BillingPlanId": 1,
        "OfferId": 0,
        "PromotionId": 0,
        "PremiumGiftId": 0,
        "Phone": "7608897387",
        "CompanyName": "",
        "ExternalSubscriptionBillingPlanId": null,
        "PaymentMethodId": 19042,
        "ExternalSubscriptionPaymentMethodId": "CIRC_28488",
        "PaymentMethod": {
          "PaymentMethodId": 19042,
          "ExternalPaymentMethodId": "CIRC_28488",
          "HolderName": "STEVE & JILL RAGEN",
          "Active": true,
          "PaymentMethodType": null,
          "FirstName": "STEVE & JILL",
          "LastName": "RAGEN",
          "CompanyName": null,
          "Phone": "7608897387",
          "BillingAddress": {
            "AddressId": 14267,
            "ExternalAddressId": null,
            "FullName": null,
            "FirstName": "STEVE & JILL",
            "LastName": "RAGEN",
            "Company": null,
            "Address": "13051 CASCO RD ",
            "Address2": null,
            "HouseNumber": "13051",
            "StreetName": "CASCO",
            "StreetSuffix": "RD",
            "PreDirect": "     ",
            "PostDirect": "",
            "AptNumber": null,
            "AptUnit": " ",
            "UnitType": null,
            "District": null,
            "City": "APPLE VALLEY",
            "CityCode": null,
            "State": "CA",
            "ZipCode": "92308",
            "ZipCode4": "4434",
            "DPVCode": null,
            "SuiteStatus": "V",
            "DeliveryPointCheckDigit": "7",
            "DPVFootnotes": "AABB",
            "DeliveryPointCode": null,
            "CountyFips": null,
            "Msa": "",
            "PakHash": "f66881d8a769124801e4ca9a3097d2f4",
            "ParsedAddressKey": "00000130510000RD00CASCO00000000000092308",
            "StandardizationError": null,
            "StandardizationResult": null,
            "Latitude": "34.488317",
            "Longitude": "-117.216829",
            "CensusBlock": "2040",
            "CensusTract": "009711",
            "GeoCoderResult": null,
            "CarrierRoute": "C017",
            "CountryCode": "US",
            "Country": null,
            "LockBox": null,
            "PhoneAC": "760",
            "PhoneEX": "889",
            "PhoneEXT": "7387",
            "Phone": "7608897387",
            "Route": null,
            "Title": null,
            "AddressTypeCode": null,
            "AddressType": null,
            "DependentLocality": null
          }
        },
        "DeliveryAddress": {
          "AddressId": 14267,
          "ExternalAddressId": null,
          "FullName": null,
          "FirstName": "STEVE & JILL",
          "LastName": "RAGEN",
          "Company": null,
          "Address": "13051 CASCO RD ",
          "Address2": null,
          "HouseNumber": "13051",
          "StreetName": "CASCO",
          "StreetSuffix": "RD",
          "PreDirect": "     ",
          "PostDirect": "",
          "AptNumber": null,
          "AptUnit": " ",
          "UnitType": null,
          "District": null,
          "City": "APPLE VALLEY",
          "CityCode": null,
          "State": "CA",
          "ZipCode": "92308",
          "ZipCode4": "4434",
          "DPVCode": null,
          "SuiteStatus": "V",
          "DeliveryPointCheckDigit": null,
          "DPVFootnotes": "AABB",
          "DeliveryPointCode": null,
          "CountyFips": null,
          "Msa": "",
          "PakHash": "f66881d8a769124801e4ca9a3097d2f4",
          "ParsedAddressKey": "00000130510000RD00CASCO00000000000092308",
          "StandardizationError": null,
          "StandardizationResult": null,
          "Latitude": "34.488317",
          "Longitude": "-117.216829",
          "CensusBlock": "2040",
          "CensusTract": "009711",
          "GeoCoderResult": null,
          "CarrierRoute": "C017",
          "CountryCode": "US",
          "Country": null,
          "LockBox": null,
          "PhoneAC": "760",
          "PhoneEX": "889",
          "PhoneEXT": "7387",
          "Phone": "7608897387",
          "Route": null,
          "Title": null,
          "AddressTypeCode": null,
          "AddressType": null,
          "DependentLocality": null
        },
        "BillingAddress": {
          "AddressId": 14267,
          "ExternalAddressId": null,
          "FullName": null,
          "FirstName": "STEVE & JILL",
          "LastName": "RAGEN",
          "Company": null,
          "Address": "13051 CASCO RD ",
          "Address2": null,
          "HouseNumber": "13051",
          "StreetName": "CASCO",
          "StreetSuffix": "RD",
          "PreDirect": "     ",
          "PostDirect": "",
          "AptNumber": null,
          "AptUnit": " ",
          "UnitType": null,
          "District": null,
          "City": "APPLE VALLEY",
          "CityCode": null,
          "State": "CA",
          "ZipCode": "92308",
          "ZipCode4": "4434",
          "DPVCode": null,
          "SuiteStatus": "V",
          "DeliveryPointCheckDigit": "7",
          "DPVFootnotes": "AABB",
          "DeliveryPointCode": null,
          "CountyFips": null,
          "Msa": "",
          "PakHash": "f66881d8a769124801e4ca9a3097d2f4",
          "ParsedAddressKey": "00000130510000RD00CASCO00000000000092308",
          "StandardizationError": null,
          "StandardizationResult": null,
          "Latitude": "34.488317",
          "Longitude": "-117.216829",
          "CensusBlock": "2040",
          "CensusTract": "009711",
          "GeoCoderResult": null,
          "CarrierRoute": "C017",
          "CountryCode": "US",
          "Country": null,
          "LockBox": null,
          "PhoneAC": "760",
          "PhoneEX": "889",
          "PhoneEXT": "7387",
          "Phone": "7608897387",
          "Route": null,
          "Title": null,
          "AddressTypeCode": null,
          "AddressType": null,
          "DependentLocality": null
        },
        "MerchantId": null,
        "Active": true,
        "HasPrintProducts": true,
        "HasDigitalProducts": true,
        "HasGoogleProducts": true,
        "Status": "L",
        "StatusDescription": "Active",
        "StartDate": "2014-05-06T00:00:00",
        "StopDate": null,
        "ExpirationDate": null,
        "NewspaperId": 2,
        "NewspaperName": "Valley City Press",
        "PaperCode": "VCP",
        "Products": [
          {
            "SubscriptionProductId": 8925,
            "ExternalSubscriptionProductId": null,
            "SubscriptionId": 69518,
            "ProductId": 100007,
            "StartDate": "2014-05-06T00:00:00",
            "StopDate": null,
            "Product": {
              "ProductId": 100007,
              "ExternalProductId": "100007",
              "ExternalMerchantId": "100007",
              "Name": "VCP Daily Home Delivery",
              "Price": 0,
              "Currency": null,
              "Active": true,
              "PaperCode": "VCP",
              "NewspaperId": 2,
              "ServiceTypeId": 7,
              "NewspaperBillingCode": 2,
              "IsPrint": true,
              "IsDigital": true,
              "ServiceType": {
                "ServiceTypeId": 7,
                "Name": "Mon-Sun",
                "Description": "Daily Home Delivery",
                "Sequence": 999,
                "Days": 7,
                "DeliveryMap": "1111111",
                "Code": "7Day",
                "Active": true,
                "eEditionAccess": true,
                "AllowPreviousSunday": false,
                "ServiceDays": [
                  {
                    "Day": 0,
                    "DayName": "Sunday",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  },
                  {
                    "Day": 1,
                    "DayName": "Monday",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  },
                  {
                    "Day": 2,
                    "DayName": "Tuesday",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  },
                  {
                    "Day": 3,
                    "DayName": "Wednesday",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  },
                  {
                    "Day": 4,
                    "DayName": "Thursday",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  },
                  {
                    "Day": 5,
                    "DayName": "Friday",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  },
                  {
                    "Day": 6,
                    "DayName": "Saturday",
                    "PrintAllowed": true,
                    "DigitalAllowed": true
                  }
                ]
              },
              "Discount": null,
              "Description": "VCP Daily Home Delivery",
              "IsAddOn": false,
              "DeliveryMethod": null,
              "OneTimeCharge": false,
              "RegularRate": null,
              "CircSystemId": 1,
              "BusinessName": "Daily Home Delivery",
              "Code": null,
              "RenewalProductId": null,
              "RenewalProduct": null,
              "GoogleProducts": [
                {
                  "Id": 1,
                  "Code": "dev-swg-sandbox-connext.azurewebsites.net:basic",
                  "Description": "Naviga Demo basic",
                  "GooglePublication": {
                    "Id": 1,
                    "Code": "dev-swg-sandbox-connext.azurewebsites.net",
                    "Description": "Naviga Dev Sandbox"
                  }
                }
              ],
              "IsBase": true
            },
            "Amount": 0,
            "Currency": null,
            "CampaignId": null,
            "CampaignCode": null,
            "IsAutoRenewal": false,
            "Cycles": 0,
            "Copies": 1,
            "RemainingCycles": 0,
            "MatherPrice": null,
            "MatherDate": null,
            "MatherAlternativePrices": []
          }
        ],
        "FutureProducts": [],
        "OldProducts": [],
        "NewStartQueueId": 0,
        "CirculationSystemAccountId": null,
        "DateCreated": null,
        "ProcessingStatus": null,
        "TransactionType": null,
        "RateCode": "VCP7DHDLG",
        "HouseholdSubscriptionLevel": 11,
        "UpgradeSmartOfferSegment": null,
        "DowngradeSmartOfferSegment": null,
        "SubscriptionType": "H",
        "Sub3Code": null,
        "PromoCert": null,
        "PromoCredit": null,
        "PromoSource": null,
        "PromoSubSource": null,
        "StartSource": null,
        "StartReason": null,
        "StopSource": null,
        "StopReason": null,
        "IsEZPay": false,
        "HaseBill": false,
        "IsTerm": null,
        "IsTrial": false,
        "PaymentFlag": null,
        "DailyRate": 0,
        "DeliveryMethod": null,
        "BillingMethod": "Office Pay",
        "WeekDayCredit": null,
        "SundayCredit": null,
        "IsCompSubscription": null,
        "IsMailSubscription": false,
        "DailyRateWithTaxes": 0,
        "UpgradeSubscriptionPromotionId": null,
        "DowngradeSubscriptionPromotionId": null,
        "UpgradeProductsPromotionId": null,
        "SubscriptionDescription": null,
        "BaseProduct": {
          "ProductId": 100007,
          "ExternalProductId": "100007",
          "ExternalMerchantId": "100007",
          "Name": "VCP Daily Home Delivery",
          "Price": 0,
          "Currency": null,
          "Active": true,
          "PaperCode": "VCP",
          "NewspaperId": 2,
          "ServiceTypeId": 7,
          "NewspaperBillingCode": 2,
          "IsPrint": true,
          "IsDigital": true,
          "ServiceType": {
            "ServiceTypeId": 7,
            "Name": "Mon-Sun",
            "Description": "Daily Home Delivery",
            "Sequence": 999,
            "Days": 7,
            "DeliveryMap": "1111111",
            "Code": "7Day",
            "Active": true,
            "eEditionAccess": true,
            "AllowPreviousSunday": false,
            "ServiceDays": [
              {
                "Day": 0,
                "DayName": "Sunday",
                "PrintAllowed": true,
                "DigitalAllowed": true
              },
              {
                "Day": 1,
                "DayName": "Monday",
                "PrintAllowed": true,
                "DigitalAllowed": true
              },
              {
                "Day": 2,
                "DayName": "Tuesday",
                "PrintAllowed": true,
                "DigitalAllowed": true
              },
              {
                "Day": 3,
                "DayName": "Wednesday",
                "PrintAllowed": true,
                "DigitalAllowed": true
              },
              {
                "Day": 4,
                "DayName": "Thursday",
                "PrintAllowed": true,
                "DigitalAllowed": true
              },
              {
                "Day": 5,
                "DayName": "Friday",
                "PrintAllowed": true,
                "DigitalAllowed": true
              },
              {
                "Day": 6,
                "DayName": "Saturday",
                "PrintAllowed": true,
                "DigitalAllowed": true
              }
            ]
          },
          "Discount": null,
          "Description": "VCP Daily Home Delivery",
          "IsAddOn": false,
          "DeliveryMethod": null,
          "OneTimeCharge": false,
          "RegularRate": null,
          "CircSystemId": 1,
          "BusinessName": "Daily Home Delivery",
          "Code": null,
          "RenewalProductId": null,
          "RenewalProduct": null,
          "GoogleProducts": [
            {
              "Id": 1,
              "Code": "dev-swg-sandbox-connext.azurewebsites.net:basic",
              "Description": "Naviga Demo basic",
              "GooglePublication": {
                "Id": 1,
                "Code": "dev-swg-sandbox-connext.azurewebsites.net",
                "Description": "Naviga Dev Sandbox"
              }
            }
          ],
          "IsBase": true
        },
        "DeliveryStartDate": null,
        "EffectiveStartDate": null,
        "PermanentStopDate": null,
        "CurrentBalance": null,
        "DatePaidThru": null,
        "CurrentRate": 0,
        "ExpirationDateOverride": null,
        "GraceDays": null,
        "SubscriptionStopReason": null,
        "SubscriptionSmartOffers": [
          {
            "SmartOfferId": 31079,
            "SmartOfferCode": "VCPDN",
            "SmartOfferType": "DNGRD",
            "SmartOfferSource": "G2D"
          },
          {
            "SmartOfferId": 77560,
            "SmartOfferCode": "STVCPDN",
            "SmartOfferType": "StopSaver",
            "SmartOfferSource": "G2D"
          },
          {
            "SmartOfferId": 93248,
            "SmartOfferCode": "STVCPSUN",
            "SmartOfferType": "StopSaver",
            "SmartOfferSource": "G2D"
          }
        ],
        "CustomerSince": null,
        "Market": null,
        "SubscriberType": null,
        "BillingState": null,
        "eBillEmail": "",
        "eBillEmailType": null,
        "AutobillStatus": null,
        "WeeklyRate": null,
        "RegistrationCount": null,
        "IsSeasonal": false,
        "IsExternal": false,
        "Currency": "USD",
        "CurrencySymbol": "$",
        "CurrencyCulture": "en-US",
        "CircSystemId": 1,
        "CircSystemCode": null,
        "CircSystemName": null
      }
    ],
    "GuestSubscriptions": null,
    "InactiveOwnedSubscriptions": null,
    "InactiveGuestSubscriptions": null
  },
  "SessionId": "29d787bc-5e8b-4d48-ad22-52f24bf2a03e",
  "RequestId": "0"
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










## Create a subscription

The app calls Naviga API to create subscription. Try out the API with the  Swagger link below: 

https://test.subscriberconcierge.com/swagger/ui/index#!/Subscriptions/Subscriptions_CreateSubscription 

The minimum required values for Naviga 2.x:

```
“CustomerRegistrationId”:  

“PaymentmethodID”:

"EmailAddress”:

"PlanId": [OFFER CODE], 

"PromotionId":  , 

"StartType":"NewStart", 

"StartDate": [not required, today by default] 

“iTunesInfo”: OR “GooglePlayInfo”
```

The minimum required values for Naviga 3.x:

```
“CustomerRegistrationId”:  

“PaymentmethodID”: 

"EmailAddress”:  

"OfferId": [OFFER ID], 

"OfferGroupId": [OFFER  GROUP ID], 

"StartType":"InApp", 

"StartDate": [not required, today by default] 

“iTunesInfo”: OR “GooglePlayInfo” 
```

The `iTunesInfo` below is the complete response from iTunes purchase response (see the examples).

The client should provide the Credentials for the Store – Test and Prod instance. The credentials for iTunes and Google are stored in mg2_control settings: 

- Apple.VerifySecret (iTunes) 

- ExternalPaymentWebhook.AuthToken (GooglePlay) 

### Receipt Examples

#### Google Play

```JSON
{ 

   "CustomerRegistrationId":"8399", 

   "EmailAddress":"test123@mailinator.com", 

   "OfferId":28271, 

   "OfferGroupId":12115, 

   "ActivateEZPay":true, 

   "PaymentMethodId":"", 

   "PaymentTypeId":32, 

   "StartDate":"2019-10-09", 

   "StartType":"InApp", 

   "GooglePlayInfo":{ 

      "Receipt":"{\r\n\t\"orderId\": \"GPA.3383-0177-7993-52360\",\r\n\t\"packageName\": \"com.apptivateme.next.ct\",\r\n\t\"productId\": \"2476486697\",\r\n\t\"purchaseTime\": 1508247106192,\r\n\t\"purchaseState\": 0,\r\n\t\"developerPayload\": \"Get+unlimited+access+to+the+Chicago+Tribune+app+and+chicagotribune.com0\",\r\n\t\"purchaseToken\": \"ekghdeppdchnbecdmopogocm.AO-J1Oy0wv7jCSu6zxj1AVR_INdJCSBvDSZH2arPT3uR36JWZXaXx1G-5KrFe8X91DaQFkzPB-gOb7FiZlI6zsYRArElFHUAaFzaiTN0U64ygmwNGea96E_hqu2mMm_bpu1o8VK4XmE1\",\r\n\t\"autoRenewing\": true\r\n}" 

   } 

}
```

#### iTunes

```JSON
{ 

   "CustomerRegistrationId":"869", 

   "EmailAddress":"nporoshin@marketingg2.com", 

   "OfferID":68, 

   "OfferGroupID":89, 

   "PaymentMethodId":"", 

   "PaymentTypeId":31, 

   "StartDate":"2018-10-31", 

   "StartType":"InApp", 

   "iTunesInfo":{ 

      "Receipt":"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" 

   } 

} 
```

### Additional Information

The app can also call Naviga's API to get an offer instead of storing the offer and promotion id. Please reach out to Naviga for more details.

The client can pass more details in add subscription call. Please find below json details below:

```json
{
  "CustomerRegistrationId": "1009",
  "EmailAddress": "1@1.com",
  "PlanId": 15,
  "PromotionId": 5,
  "GiftId": 0,
  "DeliveryAddress": null,
  "BillingAddress": {
    "AddressId": 0,
    "ExternalAddressId": null,
    "FullName": "Slava Kutcher",
    "FirstName": "Slava",
    "LastName": "Kutcher",
    "Company": "",
    "Address": "400 N River Rd",
    "HouseNumber": null,
    "StreetName": null,
    "StreetSuffix": null,
    "PreDirect": null,
    "PostDirect": null,
    "AptNumber": null,
    "AptUnit": "Apt 605",
    "UnitType": null,
    "District": null,
    "City": "West Lafayette",
    "CityCode": null,
    "State": "IN",
    "ZipCode": "47906",
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
    "Phone": "4444445675",
    "Route": null,
    "Title": null
  },
  "PaymentTypeId": 1,
  "CreditCard": {
    "Type": "VISA",
    "Number": "411111******1111",
    "NumberFirstTwoDigits": "",
    "NumberLastFourDigits": "4111",
    "ExpirationMonth": "10",
    "ExpirationYear": "20",
    "SecurityCode": null,
    "OwnerName": "Slava;yghl; Kutcher"
  },
  "BankAccount": null,
  "PayPalInfo": null,
  "ActivateEZPay": true,
  "Amount": {
    "AmountCharged": 9.99,
    "ActivationFee": 0,
    "TaxAmount": 0,
    "SubscriptionCost": 9.99
  },
  "RecurringPaymentDayOfMonth": 0,
  "PaymentMethodId": "033806411",
  "StartDate": "2018-10-11T07:21:59",
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
      "ExternalProductId": "100066",
      "MerchantProductId": null,
      "ProductQuantity": 1
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
  "InitialCredit": null
}
```

### Webhooks for Google, iTunes and Amazon

To maintain the subscription status, push notifications must be sent to the following endpoint for Google Play and iTunes:  

> https://prod.subscriberconcierge.com/Notifications/{provider}/{mediaGroup}/{clientCode}/{paperCode} 

The provider would be one of the following:

* iTunes
* GooglePlay

Please reach out to your PM for your specific MediaGroup, ClientCode & Papercode settings.

Once you have received your push notification endpoints, the client must follow the documentation below to setup these up in their GooglePlay or iTunes console. Please refer to the following documentation.

#### Google Play documentation

Google Notifications leverages the use of Google Cloud Pub/Sub. See the following link to configure the Topics and Subscriptions: 

https://developer.android.com/google/play/billing/getting-ready 

Subscribe exposes an endpoint to receive the notifications at any time. This means that the Subscription needs to be configured as a Push. 

https://cloud.google.com/pubsub/docs/push 

> **NOTE**: Originally, Google requested for confirmation on domain ownership by generating a unique confirmation file to be installed on the servers. Google has discontinued this.

MG2Control setting: `ExternalPaymentWebhook.AuthToken ` 

Supported notifications:

* `SUBSCRIPTION_CANCELED`
* `SUBSCRIPTION_DEFERRED`
* `SUBSCRIPTION_ON_HOLD`
* `SUBSCRIPTION_PRICE_CHANGE_CONFIRMED`
* `SUBSCRIPTION_RECOVERED`
* `SUBSCRIPTION_RENEWED`
* `SUBSCRIPTION_RESTARTED`

> **NOTE**: All notifications except s`ubscription_canceled` and `subscription_restarted` are ignored by Naviga in Google Play. 

#### iTunes documentation

https://developer.apple.com/documentation/storekit/in-app_purchase/enabling_server-to-server_notifications 

Mg2Control setting: Apple.VerifySecret 

> **NOTE**: In iTunes, only `cancel`, `interactive_renewal`, and `did_change_renewal_pref` are processed by Naviga. The remaining are ignored. 

#### Amazon Pay

To maintain subscription status, Naviga has created a nightly process that calls Amazon and updates Subscribe db. For each active `ReceiptId`, the process sends a verification request through the Amazon API. In response to the verification request, the subscription status is active, canceled, or restarted in Naviga.  

Clients will have to configure `ClientId` and `ClientSecret` in the Amazon developer console:
 https://developer.amazon.com/ (Settings -> Security Profile) 
 https://prnt.sc/rhyrdf so Naviga can access Amazon API. 

Mg2Control settings: `Amazon.ClientId` and `Amazon.ClientSecret`
# Health Quote FE Spec (Exact Payloads Only)

This document uses the same FE wrapper style as the shared life payload spec.
`pospUserName` must be sent at flat `data.premiumRequest.pospUserName`.
`policyType` must be sent inside `data.premiumRequest.planDetails.policyType`.

APIs:
- `POST /api/minterprise/v2/products/health/quotes`
- `GET /api/minterprise/v2/products/health/quotes?referenceId=...&includeRequest=true|false`
- `GET /api/minterprise/v2/products/health/quotes/poll?referenceId=...&resultIds=...`

---

## 1) Request payloads (exact)

## 1.1 New business, single self bucket

```json
{
  "data": {
    "premiumRequest": {
      "pospUserName": "66bb2378ae016500016e5a06",
      "personalDetails": {
        "customerName": "ABID AHMAD SHAH",
        "userMobile": "7400400747",
        "userEmail": "SHAHABID37@GMAIL.COM",
        "customerId": "8080515100"
      },
      "proposerDetails": {},
      "riskInsured": {
        "insuredMembers": [
          {
            "insuredFullName": "ABID AHMAD SHAH",
            "dateOfBirth": "1972-05-03T00:00:00+05:30",
            "entryAge": 53,
            "ageInMonths": 636,
            "gender": "M",
            "type": "self",
            "usertype": "SELF",
            "pincode": "411041",
          }
        ]
      },
      "planDetails": {
        "policyType": "FLOATER",
        "businessType": "NEW",
        "coverAmount": 1000000,
        "deductible": 0,
        "policyTerm": 1,
        "noOfAdults": 1,
        "noOfChildren": 0,
        "pincode": [
          "411041"
        ],
        "preExistingDisease": false,
        "requireMaternity": false,
        "partnerTracksLead": true,
        "saveCompleteRequest": true,
        "isPaid": "No",
        "selectedBucketName": "SELF",
        "needs": {
          "majorHealthExpenses": true
        },
        "addOnGroup": [],
        "addOns": {},
        "previousPolicyDetail": null
      },
      "bucketDetails": {
        "buckets": [
          {
            "bucketName": "SELF",
            "uniqueId": "bucket-self-1",
            "sumInsured": 1000000,
            "deductible": 0,
            "selectedPlanTypeList": [
              "BASIC"
            ],
            "selectedPlanType": "BASIC",
            "noOfAdults": 1,
            "noOfChildren": 0,
            "pincode": "411041",
            "city": "PUNE",
            "state": "MH",
            "userdetails": [
              {
                "type": "self",
                "usertype": "SELF",
                "age": 53,
                "age_months": 636,
                "gender": "M",
                "dob": "1972-05-03T00:00:00+05:30",
                "pincode": "411041"
              }
            ]
          }
        ]
      },
      "vertical": "HEALTH"
    }
  }
}
```

## 1.2 Initial request New business, family floater multi-member without buckets

```json
{
  "data": {
    "premiumRequest": {
      "pospUserName": "66bb2378ae016500016e5a06",
      "personalDetails": {
        "customerName": "asdasd",
        "customerConsentId": "",
        "userMobile": "7400400747",
        "userEmail": "shahabid37@gmail.com"
      },
      "proposerDetails": {},
      "riskInsured": {
        "insuredMembers": [
          {
            "insuredFullName": "asdasd",
            "entryAge": 24,
            "ageInMonths": 288,
            "gender": "M",
            "type": "self",
            "usertype": "SELF",
            "pincode": "411041",
            "hospitalIds": []
          },
          {
            "insuredFullName": "asdasd spouse",
            "entryAge": 24,
            "ageInMonths": 288,
            "gender": "F",
            "type": "spouse",
            "usertype": "SPOUSE",
            "pincode": "411041",
            "hospitalIds": []
          },
          {
            "insuredFullName": "asdasd mother",
            "entryAge": 41,
            "ageInMonths": 492,
            "gender": "F",
            "type": "mother",
            "usertype": "MOTHER",
            "pincode": "411041",
            "hospitalIds": []
          },
          {
            "insuredFullName": "asdasd father",
            "entryAge": 41,
            "ageInMonths": 492,
            "gender": "M",
            "type": "father",
            "usertype": "FATHER",
            "pincode": "411041",
            "hospitalIds": []
          },
          {
            "insuredFullName": "asdasd son",
            "entryAge": 0,
            "ageInMonths": 11,
            "gender": "M",
            "type": "son",
            "usertype": "SON1",
            "pincode": "411041",
            "hospitalIds": []
          }
        ]
      },
      "planDetails": {
        "policyType": "MULTI_INDIVIDUAL",
        "businessType": "NEW",
        "coverAmount": 1000000,
        "firstName": "asdasd",
        "noOfAdults": 4,
        "noOfChildren": 1,
        "pincode": [
          "411041",
          "411041"
        ],
        "preExistingDisease": false,
        "requireMaternity": false,
        "partnerTracksLead": true,
        "saveCompleteRequest": true,
        "isPaid": "No",
        "needs": {
          "majorHealthExpenses": true
        },
        "hospitalsIds": {
          "411041": []
        }
      },
      "initialReqFlag": true,
      "isAsync": true,
      "requestType": "INITIAL",
      "vertical": "HEALTH"
    }
  }
}
```
---

## 1.3 New request New business, family floater multi-member with buckets
```json
{
  "data": {
    "referenceId": "AHW41N05KP9",
    "premiumRequest": {
      "pospUserName": "66bb2378ae016500016e5a06",
      "personalDetails": {
        "customerName": "asdasd",
        "customerConsentId": "",
        "userMobile": "7400400747",
        "userEmail": "shahabid37@gmail.com"
      },
      "proposerDetails": {},
      "riskInsured": {
        "insuredMembers": [
          {
            "insuredFullName": "asdasd",
            "entryAge": 24,
            "ageInMonths": 288,
            "gender": "M",
            "type": "self",
            "usertype": "SELF",
            "pincode": "411041",
            "hospitalIds": []
          },
          {
            "insuredFullName": "asdasd spouse",
            "entryAge": 24,
            "ageInMonths": 288,
            "gender": "F",
            "type": "spouse",
            "usertype": "SPOUSE",
            "pincode": "411041",
            "hospitalIds": []
          },
          {
            "insuredFullName": "asdasd mother",
            "entryAge": 41,
            "ageInMonths": 492,
            "gender": "F",
            "type": "mother",
            "usertype": "MOTHER",
            "pincode": "411041",
            "hospitalIds": []
          },
          {
            "insuredFullName": "asdasd father",
            "entryAge": 41,
            "ageInMonths": 492,
            "gender": "M",
            "type": "father",
            "usertype": "FATHER",
            "pincode": "411041",
            "hospitalIds": []
          },
          {
            "insuredFullName": "asdasd son",
            "entryAge": 0,
            "ageInMonths": 11,
            "gender": "M",
            "type": "son",
            "usertype": "SON1",
            "pincode": "411041",
            "hospitalIds": []
          }
        ]
      },
      "planDetails": {
        "policyType": "FAMILY_FLOATER",
        "businessType": "NEW",
        "coverAmount": 1000000,
        "coverType": "FAMILY_FLOATER",
        "deductible": 0,
        "firstName": "asdasd",
        "maternityDateMonths": 0,
        "noOfAdults": 4,
        "noOfChildren": 1,
        "pincode": [
          "411041",
          "411041"
        ],
        "preExistingDisease": false,
        "requireMaternity": false,
        "partnerTracksLead": true,
        "saveCompleteRequest": true,
        "isPaid": "No",
        "selectedBucketName": "all_members",
        "needs": {
          "majorHealthExpenses": true,
          "maternity": false,
          "diseaseCover": false,
          "seniorCitizen": false,
          "upgradeCover": false,
          "changeInsurer": false
        },
        "hospitalsIds": {
          "411041": []
        }
      },
      "bucketDetails": {
        "buckets": [
          {
            "uniqueId": "dfafb1ef-82cf-4d4e-bc0c-1804143ff0f0",
            "noOfAdults": 4,
            "noOfChildren": 1,
            "sumInsured": 1000000,
            "deductible": 0,
            "selectedPlanTypeList": [
              "B"
            ],
            "userdetails": [
              {
                "age": 24,
                "age_months": 288,
                "type": "self",
                "usertype": "SELF",
                "gender": "M"
              },
              {
                "age": 24,
                "age_months": 288,
                "type": "spouse",
                "usertype": "SPOUSE",
                "gender": "F"
              },
              {
                "age": 41,
                "age_months": 492,
                "type": "mother",
                "usertype": "MOTHER",
                "gender": "F"
              },
              {
                "age": 41,
                "age_months": 492,
                "type": "father",
                "usertype": "FATHER",
                "gender": "M"
              },
              {
                "age": 0,
                "age_months": 11,
                "type": "son",
                "usertype": "SON1",
                "gender": "M"
              }
            ],
            "year": 1,
            "bucketName": "all_members",
            "pincode": "411041",
            "latitude": "18.4601666",
            "longitude": "73.8114873",
            "city": "Pune",
            "state": "Maharashtra",
            "healthPricingRequestId": "AHW41N05KP9",
            "hospitalIds": [],
            "preExistDisease": false,
            "coverType": "FAMILY_FLOATER",
            "defaultSelectedBucket": true
          },
          {
            "uniqueId": "dfafb1ef-82cf-4d4e-bc0c-1804143ff0f0",
            "needs": {
              "majorHealthExpenses": true,
              "maternity": false,
              "diseaseCover": false,
              "seniorCitizen": false,
              "upgradeCover": false,
              "changeInsurer": false
            },
            "noOfAdults": 2,
            "noOfChildren": 1,
            "sumInsured": 1000000,
            "deductible": 0,
            "selectedPlanTypeList": [
              "B"
            ],
            "selectedPlanType": "B",
            "userdetails": [
              {
                "age": 24,
                "age_months": 288,
                "type": "self",
                "usertype": "SELF",
                "gender": "M"
              },
              {
                "age": 24,
                "age_months": 288,
                "type": "spouse",
                "usertype": "SPOUSE",
                "gender": "F"
              },
              {
                "age": 0,
                "age_months": 11,
                "type": "son",
                "usertype": "SON1",
                "gender": "M"
              }
            ],
            "year": 1,
            "bucketName": "self_spouse_1kids",
            "pincode": "411041",
            "latitude": "18.4601666",
            "longitude": "73.8114873",
            "city": "Pune",
            "state": "Maharashtra",
            "healthPricingRequestId": "AHW41N05KP9",
            "hospitalIds": [],
            "preExistDisease": false,
            "coverType": "FAMILY_FLOATER",
            "defaultSelectedBucket": false
          },
          {
            "uniqueId": "dfafb1ef-82cf-4d4e-bc0c-1804143ff0f0",
            "needs": {
              "majorHealthExpenses": true,
              "maternity": false,
              "diseaseCover": false,
              "seniorCitizen": false,
              "upgradeCover": false,
              "changeInsurer": false
            },
            "noOfAdults": 2,
            "noOfChildren": 0,
            "sumInsured": 1000000,
            "deductible": 0,
            "selectedPlanTypeList": [
              "B"
            ],
            "selectedPlanType": "B",
            "userdetails": [
              {
                "age": 41,
                "age_months": 492,
                "type": "mother",
                "usertype": "MOTHER",
                "gender": "F"
              },
              {
                "age": 41,
                "age_months": 492,
                "type": "father",
                "usertype": "FATHER",
                "gender": "M"
              }
            ],
            "year": 1,
            "bucketName": "parents",
            "pincode": "411041",
            "latitude": "18.4601666",
            "longitude": "73.8114873",
            "city": "Pune",
            "state": "Maharashtra",
            "healthPricingRequestId": "AHW41N05KP9",
            "hospitalIds": [],
            "preExistDisease": false,
            "coverType": "FAMILY_FLOATER",
            "defaultSelectedBucket": false
          }
        ]
      },
      "initialReqFlag": true,
      "isAsync": true,
      "requestType": "INITIAL",
      "vertical": "HEALTH"
    }
  }
}
```

---

## 2) Final response structure (for FE)

Wrapper:

```json
{
  "data": { "...QuotationResponse...": "..." },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "..."
  }
}
```

`data` fields:
- `productCode`
- `referenceId`
- `status`
- `error`
- `pendingKeyList`
- `premiumRequest`
- `validationMap`
- `healthAddOnValidationInfo`
- `quotes`
- `transactionSource`
- `transactionMode`

`data.quotes[*]` fields:
- `_id`, `referenceId`, `provider`, `productCode`, `planCode`, `quoteId`
- `partnerId`, `tenant`, `broker`, `status`
- `leadName`, `insurerName`, `insurerCode`
- `premium`, `tax`, `totalPremium`, `netPremium`, `currency`, `sumInsured`, `policyTerm`
- `riskInsured`, `planName`, `stage`
- `validationMap`, `pendingKeyList`, `errorMessage`
- `premiumResponse`

`premiumResponse` contains:
- identity/status fields (`requestId`, `uniqueId`, `bucketName`, `insurerCode`, `premiumStatus`, `message`)
- location fields (`pincode`, `city`, `state`, `latitude`, `longitude`)
- requested values (`requestedCoverAmount`, `requestedDeductible`)
- quote summary fields (`planName`, `productName`, `claimOfSpeedInOneMonth`, `tags`)
- health plan variants under `pricingPlans[]`
- portability / addon / additional fields when present

`premiumResponse.pricingPlans[*]` contains:
- `quoteId`, `insurerCode`, `insurerName`
- `sumInsured`, `planId`, `planName`, `planType`, `planCode`, `planKey`
- `policyTerm`, `coverType`, `businessType`
- `totalPremium`, `basicPremium`, `serviceTax`, `discount`, `grossPremium`
- `recommended`, `resultSummary`, `healthBenefitFilters`
- `premiumStatus`, `message`, `errorCategory`, `categorisedErrorMessage`
- `addOns`

---

## 3) Response examples

### 3.1 Pending

```json
{
  "data": {
    "productCode": "health",
    "referenceId": "AHW-PEND-1",
    "pendingKeyList": [
      "SELF$niva-health"
    ],
    "quotes": [
      {
        "_id": "RID-P-1",
        "quoteId": "QID-P-1",
        "status": "pending",
        "planCode": "SELF$niva-health",
        "premiumResponse": {
          "bucketName": "SELF",
          "insurerCode": "NIVA",
          "premiumStatus": "PENDING",
          "message": "QUOTE_IN_PROGRESS",
          "pricingPlans": []
        }
      }
    ],
    "transactionSource": "API",
    "transactionMode": "ONLINE"
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "..."
  }
}
```

### 3.2 Success with pricing plans

```json
{
  "data": {
    "productCode": "health",
    "referenceId": "AHW-S-1",
    "pendingKeyList": [],
    "quotes": [
      {
        "_id": "RID-S-1",
        "quoteId": "QID-S-1",
        "status": "success",
        "planCode": "SELF$care-health",
        "premiumResponse": {
          "requestId": "AHW-S-1",
          "uniqueId": "bucket-self-1",
          "bucketName": "SELF",
          "insurerCode": "CARE",
          "planName": "Care Supreme",
          "premiumStatus": "SUCCESS",
          "requestedCoverAmount": 1000000,
          "requestedDeductible": 0,
          "pincode": "411041",
          "city": "PUNE",
          "state": "MH",
          "claimOfSpeedInOneMonth": 96.4,
          "tags": [
            "cashless",
            "recommended"
          ],
          "pricingPlans": [
            {
              "quoteId": "insurer-quote-1",
              "insurerCode": "CARE",
              "insurerName": "Care Health",
              "sumInsured": 1000000,
              "planId": "care-supreme",
              "planName": "Care Supreme",
              "planType": "BASIC",
              "planCode": "care-supreme",
              "planKey": "SELF.care-supreme.1",
              "policyTerm": 1,
              "coverType": "FLOATER",
              "businessType": "NEW",
              "totalPremium": 12456,
              "basicPremium": 10556,
              "serviceTax": 1900,
              "discount": 0,
              "grossPremium": 12456,
              "recommended": true,
              "resultSummary": [
                "Cashless network",
                "Room rent covered"
              ],
              "healthBenefitFilters": {
                "cashless": true,
                "maternity": false
              },
              "premiumStatus": "SUCCESS",
              "message": "Success",
              "addOns": {}
            }
          ]
        }
      }
    ]
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "..."
  }
}
```

### 3.3 Failure

```json
{
  "data": {
    "productCode": "health",
    "referenceId": "AHW-F-1",
    "pendingKeyList": [],
    "quotes": [
      {
        "_id": "RID-F-1",
        "quoteId": "QID-F-1",
        "status": "failed",
        "planCode": "SELF$max-health",
        "errorMessage": "INTERNAL_HEALTH_SERVICE_ERROR",
        "premiumResponse": {
          "bucketName": "SELF",
          "insurerCode": "MAX",
          "premiumStatus": "ERROR",
          "message": "INTERNAL_HEALTH_SERVICE_ERROR",
          "pricingPlans": []
        }
      }
    ]
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "..."
  }
}
```

### 3.4 Multiple quotes (mixed)

```json
{
  "data": {
    "productCode": "health",
    "referenceId": "AHW-MIX-1",
    "pendingKeyList": [
      "SELF$niva-health"
    ],
    "quotes": [
      {
        "_id": "RID-M-1",
        "quoteId": "QID-M-1",
        "status": "success",
        "planCode": "SELF$care-health",
        "premiumResponse": {
          "bucketName": "SELF",
          "insurerCode": "CARE",
          "premiumStatus": "SUCCESS"
        }
      },
      {
        "_id": "RID-M-2",
        "quoteId": "QID-M-1",
        "status": "pending",
        "planCode": "SELF$niva-health",
        "premiumResponse": {
          "bucketName": "SELF",
          "insurerCode": "NIVA",
          "premiumStatus": "PENDING"
        }
      },
      {
        "_id": "RID-M-3",
        "quoteId": "QID-M-1",
        "status": "failed",
        "planCode": "SELF$max-health",
        "premiumResponse": {
          "bucketName": "SELF",
          "insurerCode": "MAX",
          "premiumStatus": "ERROR"
        }
      }
    ]
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "..."
  }
}
```

---

## 4) GET /quotes and /poll

- `GET /quotes` response is same shape as POST response.
- with `includeRequest=true`, response additionally includes `data.premiumRequest`.
- `GET /quotes/poll` response is same shape as POST response.
- FE keeps polling until `pendingKeyList` is empty.

---

## 5) Final response update (authoritative)

Important final response rules:
- `data.premiumRequest` is returned because health FE uses it to drive bucket-aware results and filters.
- `data.validationMap` is returned because health FE uses it for quote orchestration and polling.
- `data.healthAddOnValidationInfo` is returned when addon validation metadata exists.
- `data.quotes` can contain `SUCCESS`, `PENDING`, and `ERROR` rows for bucket/product-key level visibility.
- `pendingKeyList` tracks unfinished quote keys and is used by poll API.
- `premiumResponse` is the normalized health quote payload for a quote row.
- `pricingPlans[]` carries insurer plan variants for the quote row.

## 6) Complete full response JSON (authoritative)

```json
{
  "data": {
    "productCode": "health",
    "referenceId": "AHW3RVJ9M9U",
    "status": "success",
    "error": null,
    "pendingKeyList": [
      "SELF$niva-health"
    ],
    "premiumRequest": {
      "_id": "AHW3RVJ9M9U",
      "uniqueId": "bucket-self-1",
      "vertical": "HEALTH",
      "policyType": "FLOATER",
      "customerName": "asd",
      "userMobile": "7400400747",
      "userEmail": "shahabid37@gmail.com",
      "pospUserName": "66bb2378ae016500016e5a06",
      "healthPricingRequest": {
        "pricingRequestId": "AHW3RVJ9M9U",
        "businessType": "NEW",
        "coverAmount": 1000000,
        "deductible": 0,
        "policyTerm": 1,
        "selectedBucketName": "SELF",
        "insuredMembers": [
          {
            "age": 53,
            "age_months": 636,
            "gender": "M",
            "pincode": "411041",
            "type": "self",
            "usertype": "SELF"
          }
        ],
        "buckets": [
          {
            "bucketName": "SELF",
            "uniqueId": "bucket-self-1",
            "sumInsured": 1000000,
            "deductible": 0,
            "selectedPlanTypeList": [
              "BASIC"
            ],
            "selectedPlanType": "BASIC",
            "noOfAdults": 1,
            "noOfChildren": 0,
            "pincode": "411041",
            "city": "PUNE",
            "state": "MH"
          }
        ]
      }
    },
    "validationMap": {
      "SELF$care-health": {
        "key": "SELF$care-health",
        "insurerCode": "CARE",
        "uniqueId": "bucket-self-1",
        "productName": "Care Supreme",
        "valid": true,
        "message": "success",
        "planId": "care-supreme",
        "productCode": "care-health",
        "applicableProductVariants": [
          "care-supreme"
        ]
      },
      "SELF$niva-health": {
        "key": "SELF$niva-health",
        "insurerCode": "NIVA",
        "uniqueId": "bucket-self-1",
        "productName": "Niva ReAssure",
        "valid": true,
        "message": "success",
        "planId": "niva-reassure",
        "productCode": "niva-health",
        "applicableProductVariants": [
          "niva-reassure"
        ]
      }
    },
    "healthAddOnValidationInfo": {
      "addonGroups": []
    },
    "quotes": [
      {
        "_id": "RID-H-1",
        "referenceId": "AHW3RVJ9M9U",
        "provider": "CARE",
        "productCode": "health",
        "planCode": "SELF$care-health",
        "quoteId": "QID-H-1",
        "partnerId": "partner-id",
        "tenant": "tm",
        "broker": "tm",
        "status": "success",
        "leadName": "asd",
        "insurerName": "Care Health",
        "insurerCode": "CARE",
        "premium": 12456,
        "tax": 1900,
        "totalPremium": 12456,
        "netPremium": 10556,
        "currency": "INR",
        "sumInsured": 1000000,
        "policyTerm": 1,
        "riskInsured": {
          "bucketName": "SELF",
          "insuredMembers": [
            {
              "type": "self",
              "usertype": "SELF",
              "gender": "M",
              "age": 53
            }
          ]
        },
        "planName": "Care Supreme",
        "stage": "QUOTE",
        "premiumResponse": {
          "requestId": "AHW3RVJ9M9U",
          "uniqueId": "bucket-self-1",
          "bucketName": "SELF",
          "insurerCode": "CARE",
          "planName": "Care Supreme",
          "productName": "Care Supreme",
          "premiumStatus": "SUCCESS",
          "message": "Success",
          "requestedCoverAmount": 1000000,
          "requestedDeductible": 0,
          "pincode": "411041",
          "city": "PUNE",
          "state": "MH",
          "claimOfSpeedInOneMonth": 96.4,
          "tags": [
            "cashless",
            "recommended"
          ],
          "pricingPlans": [
            {
              "quoteId": "insurer-quote-1",
              "insurerCode": "CARE",
              "insurerName": "Care Health",
              "sumInsured": 1000000,
              "planId": "care-supreme",
              "planName": "Care Supreme",
              "planType": "BASIC",
              "planCode": "care-supreme",
              "planKey": "SELF.care-supreme.1",
              "policyTerm": 1,
              "coverType": "FLOATER",
              "businessType": "NEW",
              "totalPremium": 12456,
              "basicPremium": 10556,
              "serviceTax": 1900,
              "discount": 0,
              "grossPremium": 12456,
              "recommended": true,
              "resultSummary": [
                "Cashless network",
                "Room rent covered"
              ],
              "healthBenefitFilters": {
                "cashless": true,
                "maternity": false
              },
              "premiumStatus": "SUCCESS",
              "message": "Success",
              "errorCategory": "SUCCESS",
              "addOns": {}
            }
          ]
        }
      }
    ],
    "transactionSource": "API",
    "transactionMode": "ONLINE"
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "6997cc25a2396d59a5b88585cb8fe4d3",
    "timestamp": "2026-03-26T12:00:00.000000000"
  }
}
```

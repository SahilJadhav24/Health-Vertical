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
            "ped": {
              "hypertension": false,
              "diabetes": false,
              "heartDiseases": false,
              "otherCondition": false
            },
            "medical": {},
            "height": "170",
            "weight": "72"
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
      "utmParams": {
        "utmMedium": null,
        "utmSource": null,
        "utmUrl": "https://pro.sanity.turtle-feature.com/health-insurance/health-profile/AHW3RVJ9M9U?step=leadInfo"
      },
      "vertical": "HEALTH"
    }
  }
}
```

## 1.2 New business, family floater multi-member bucket

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
            "dateOfBirth": "1988-05-03T00:00:00+05:30",
            "entryAge": 37,
            "ageInMonths": 444,
            "gender": "M",
            "type": "self",
            "usertype": "SELF",
            "pincode": "411041"
          },
          {
            "insuredFullName": "SANA SHAH",
            "dateOfBirth": "1990-08-12T00:00:00+05:30",
            "entryAge": 35,
            "ageInMonths": 420,
            "gender": "F",
            "type": "spouse",
            "usertype": "SPOUSE",
            "pincode": "411041"
          },
          {
            "insuredFullName": "CHILD ONE",
            "dateOfBirth": "2018-02-01T00:00:00+05:30",
            "entryAge": 7,
            "ageInMonths": 84,
            "gender": "M",
            "type": "son",
            "usertype": "SON",
            "pincode": "411041"
          }
        ]
      },
      "planDetails": {
        "policyType": "FLOATER",
        "businessType": "NEW",
        "coverAmount": 1500000,
        "deductible": 0,
        "policyTerm": 1,
        "noOfAdults": 2,
        "noOfChildren": 1,
        "pincode": [
          "411041"
        ],
        "preExistingDisease": false,
        "requireMaternity": true,
        "partnerTracksLead": true,
        "saveCompleteRequest": true,
        "isPaid": "No",
        "selectedBucketName": "SELF_SPOUSE_SON",
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
            "bucketName": "SELF_SPOUSE_SON",
            "uniqueId": "bucket-family-1",
            "sumInsured": 1500000,
            "deductible": 0,
            "selectedPlanTypeList": [
              "BASIC",
              "MATERNITY"
            ],
            "selectedPlanType": "BASIC",
            "noOfAdults": 2,
            "noOfChildren": 1,
            "pincode": "411041",
            "city": "PUNE",
            "state": "MH",
            "userdetails": [
              {
                "type": "self",
                "usertype": "SELF",
                "age": 37,
                "age_months": 444,
                "gender": "M",
                "dob": "1988-05-03T00:00:00+05:30",
                "pincode": "411041"
              },
              {
                "type": "spouse",
                "usertype": "SPOUSE",
                "age": 35,
                "age_months": 420,
                "gender": "F",
                "dob": "1990-08-12T00:00:00+05:30",
                "pincode": "411041"
              },
              {
                "type": "son",
                "usertype": "SON",
                "age": 7,
                "age_months": 84,
                "gender": "M",
                "dob": "2018-02-01T00:00:00+05:30",
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

## 1.3 Portability with previous policy details

```json
{
  "data": {
    "referenceId": "AHW3RVJ9M9U",
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
            "pincode": "411041"
          }
        ]
      },
      "planDetails": {
        "policyType": "FLOATER",
        "businessType": "PORTABILITY",
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
        "previousPolicyDetail": {
          "insurerCode": "HDFCERGO",
          "insurerName": "HDFC Ergo",
          "productCode": "ergo-optima",
          "productName": "Optima Restore",
          "coverAmount": "1000000",
          "premium": "18500",
          "policyEndDate": "2026-05-31",
          "claimed": false,
          "insuredMembers": [
            "SELF"
          ]
        }
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
          "status": "SUCCESS",
          "insurerStatus": "SUCCESS",
          "insurerCode": "CARE",
          "productCode": "care-health",
          "option": "Base",
          "optionCode": 0,
          "premium": 12456,
          "tax": 1900,
          "premiumWithTax": 12456,
          "riderList": [],
          "responseOptions": [
            {
              "option": "Plus",
              "optionCode": 1,
              "status": "SUCCESS",
              "premiumWithTax": 14890
            }
          ],
          "companyDetails": {
            "insurerCode": "CARE",
            "displayName": "Care Health",
            "logo": "https://..."
          }
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
    "referenceId": "AHWHP1QQBR8",
    "pendingKeyList": [
      "SELF$niva-health"
    ],
    "quotes": [
      {
        "quoteId": "dc28c8a00890741fca957b2f92783599",
        "insurerQuoteId": "b8735fd6-0a0d-4e30-aa73-2ae1e0be8d96",
        "policyType": "FLOATER",
        "insurerCode": "CARE",
        "internalProductCode": "care-health-care-supreme",
        "productCode": "SELF$care-health",
        "productName": "Care Supreme",
        "option": "Base",
        "optionCode": 1,
        "productUIN": "UIN-CARE-SUPREME",
        "tmPlanId": "2460",
        "policyTerm": 1,
        "paymentFrequency": 1,
        "premiumPaymentTerm": 1,
        "score": 0,
        "category": "health",
        "premium": 12456,
        "taxRate": 18,
        "premiumWithTax": 12456,
        "sumAssured": 1000000,
        "deductible": 0,
        "cashlessHospitalsCount": 11432,
        "responseOptions": [
          {
            "quoteId": "6d5ffe95c64e53f849a48396c049ec80",
            "insurerQuoteId": "fdee0910-ae04-4cfc-b64b-b7556ebb74e9",
            "policyType": "FLOATER",
            "insurerCode": "CARE",
            "internalProductCode": "care-health-care-supreme",
            "productCode": "SELF$care-health",
            "productName": "Care Supreme Plus",
            "option": "Plus",
            "optionCode": 2,
            "productUIN": "UIN-CARE-SUPREME",
            "tmPlanId": "2460",
            "policyTerm": 1,
            "paymentFrequency": 1,
            "premiumPaymentTerm": 1,
            "score": 19,
            "category": "health",
            "premium": 14890,
            "taxRate": 18,
            "premiumWithTax": 14890,
            "sumAssured": 1000000,
            "deductible": 0,
            "status": "SUCCESS",
            "insurerStatus": "SUCCESS",
            "insurerMessage": "SUCCESS",
            "insurerBusinessFlowType": "QUOTES_REQUEST",
            "maternityBenefits": [
              "Enhanced maternity cover after waiting period"
            ],
            "planNote": [
              "Higher room rent eligibility",
              "Higher restore benefit"
            ],
            "planType": "Enhanced",
            "riderList": [],
            "showRider": false,
            "showRiderPremium": false,
            "cashlessHospitalsCount": 11432,
            "age": 53,
            "inputCoverAmount": 1000000,
            "planFeatureDetailsList": [],
            "bqpRedirectionEnabled": false,
            "paymentFirstJourneyCheck": false,
            "resultCardsInfo": {
              "entryAge": 53,
              "sumInsured": 1000000,
              "cashlessHospitalsCount": 11432,
              "claimSettlementRatio": "96.40%",
              "roomRent": "Single Private Room"
            },
            "planFeatureList": [
              {
                "code": "maternity",
                "name": "Maternity",
                "active": true
              }
            ],
            "errorCategory": "SUCCESS",
            "defaultOption": false,
            "specialBenefits": [
              "Air ambulance cover"
            ]
          },
          {
            "quoteId": "9f49a203f8207031a79797aff6f8c798",
            "insurerQuoteId": "3218c981-3014-4e85-b15e-5366f721303b",
            "policyType": "FLOATER",
            "insurerCode": "CARE",
            "internalProductCode": "care-health-care-supreme",
            "productCode": "SELF$care-health",
            "productName": "Care Supreme Elite",
            "option": "Elite",
            "optionCode": 3,
            "productUIN": "UIN-CARE-SUPREME",
            "tmPlanId": "2460",
            "policyTerm": 1,
            "paymentFrequency": 1,
            "premiumPaymentTerm": 1,
            "score": 34,
            "category": "health",
            "premium": 17325,
            "taxRate": 18,
            "premiumWithTax": 17325,
            "sumAssured": 1000000,
            "deductible": 0,
            "status": "SUCCESS",
            "insurerStatus": "SUCCESS",
            "insurerMessage": "SUCCESS",
            "insurerBusinessFlowType": "QUOTES_REQUEST",
            "planType": "Elite",
            "riderList": [],
            "showRider": false,
            "showRiderPremium": false,
            "cashlessHospitalsCount": 11432,
            "age": 53,
            "inputCoverAmount": 1000000,
            "planFeatureDetailsList": [],
            "bqpRedirectionEnabled": false,
            "paymentFirstJourneyCheck": false,
            "errorCategory": "SUCCESS",
            "defaultOption": false
          }
        ],
        "status": "SUCCESS",
        "insurerStatus": "SUCCESS",
        "insurerMessage": "SUCCESS",
        "insurerBusinessFlowType": "QUOTES_REQUEST",
        "companyDetails": {
          "InsurerId": "CARE",
          "InsurerName": "Care Health",
          "Logo": "CARE.jpg",
          "CompanyDetails": "Care Health Insurance is a standalone health insurer offering retail and family floater plans.",
          "ClaimSettlementRate": {
            "OneMonth": "96.40",
            "OneToThreeMonths": "2.10",
            "ThreeMonthsPlus": "1.50"
          },
          "SpeedOfClaimSettlementSummary": "96.40",
          "InsurerCode": "CARE",
          "ContactDetails": {
            "Telephone": "1800 102 4488",
            "Address": "Care Health Insurance, Gurgaon, Haryana, India."
          },
          "HealthCompanyDetails": {
            "claimSettlementRatio": "96.40%",
            "cashlessHospitalsCount": "11432",
            "inceptionYear": "2012",
            "solvencyRatio": "1.90"
          }
        },
        "maternityBenefits": [
          "No-claim bonus multiplier",
          "Annual health check-up"
        ],
        "planType": "Base",
        "riderList": [],
        "showRider": false,
        "showRiderPremium": false,
        "age": 53,
        "inputCoverAmount": 1000000,
        "planFeatureDetailsList": [],
        "bqpRedirectionEnabled": false,
        "paymentFirstJourneyCheck": false,
        "resultCardsInfo": {
          "entryAge": 53,
          "sumInsured": 1000000,
          "cashlessHospitalsCount": 11432,
          "claimSettlementRatio": "96.40%",
          "roomRent": "Single Private Room",
          "restoreBenefit": true
        },
        "errorCategory": "SUCCESS",
        "defaultOption": true,
        "specialBenefits": [
          "Unlimited e-consultation",
          "Annual health check-up"
        ]
      }
    ]
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "6997cc25a2396d59a5b88585cb8fe4d3",
    "timestamp": "2026-03-26T12:00:00.000000000"
  }
}
```

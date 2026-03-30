# Health Checkout API Payloads

This document captures the FE payload contracts for health checkout-related APIs.

API:
- `POST /api/minterprise/v2/products/health/checkout`

Wrapper:
- request body is `PayloadWrapper`
- FE should send payload inside `data`
- all health checkout fields are kept directly inside `data`

## POST Checkout Request

```json
{
  "data": {
    "_id": "AHW41N05KP9",
    "referenceId": "AHW41N05KP9",
    "premiumResultId": "RID-H-1",
    "insurerCode": "CARE",
    "productCode": "health",
    "provider": "CARE",
    "leadName": "asdasd",
    "businessType": "NEW",
    "policyTerm": 1,
    "payMode": "ONLINE",
    "couponCode": "HEALTH100",
    "proposalUrl": "",
    "transactionSource": "API",
    "transactionMode": "ONLINE",
    "personalDetails": {
      "customerName": "asdasd",
      "userMobile": "7400400747",
      "userEmail": "asdasd@gmail.com"
    },
    "registeredAddress": {
      "addressLine1": "Flat 101",
      "addressLine2": "ABC Residency",
      "addressLine3": "Near Metro",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041"
    },
    "stage": "INITIAL",
    "quoteId": "QID-H-1",
    "sumInsured": 1000000,
    "pricingRequestId": "AHW41N05KP9",
    "email": "asdasd@gmail.com",
    "mobile": "7400400747",
    "landline": "02012345678",
    "premiumAmount": "12456",
    "previousPremium": "11890",
    "basePremiumAmount": "10556",
    "totalPremiumDbl": 12456,
    "grossPremium": "12456",
    "taxAmount": "1900",
    "discount": 0,
    "discountAmount": "0",
    "serviceTax": 1900,
    "totalDiscount": 0,
    "coverAmount": "1000000",
    "deductible": "0",
    "productId": "care-supreme",
    "noOfAdults": 4,
    "noOfChildren": 1,
    "pincode": 411041,
    "pincodeZone": 2,
    "addrLine1": "Flat 101",
    "addrLine2": "ABC Residency",
    "addrLine3": "Near Metro",
    "addrLine4": "",
    "addrLine5": "",
    "city": "Pune",
    "state": "Maharashtra",
    "selectedBucketName": "all_members",
    "status": "INITIATED",
    "insuredMembers": [
      {
        "insuredFullName": "asdasd",
        "type": "self",
        "usertype": "SELF",
        "gender": "M",
        "age": 24,
        "age_months": 288,
        "dateOfBirth": "2002-03-30T00:00:00+05:30",
        "pincode": "411041",
        "hospitalIds": [],
        "ped": {
          "hypertension": false,
          "diabetes": false,
          "heartDiseases": false,
          "asthma": false,
          "obesity": false,
          "otherCondition": false,
          "otherConditionText": ""
        }
      }
    ],
    "proposer": {
      "insuredFullName": "asdasd",
      "type": "self",
      "usertype": "SELF",
      "gender": "M",
      "age": 24,
      "age_months": 288,
      "dateOfBirth": "2002-03-30T00:00:00+05:30",
      "pincode": "411041",
      "hospitalIds": [],
      "ped": {
        "hypertension": false,
        "diabetes": false,
        "heartDiseases": false,
        "asthma": false,
        "obesity": false,
        "otherCondition": false,
        "otherConditionText": ""
      }
    },
    "medicalHistory": {
      "ped_questionnaire": {
        "code": "ped_questionnaire",
        "question": "Any PED?",
        "answer": "No",
        "members": {}
      }
    },
    "planCode": "care-supreme",
    "insurerName": "Care Health",
    "planName": "Care Supreme",
    "planType": "BASIC",
    "proposalOnline": true,
    "cityCode": "280",
    "stateCode": "14",
    "completedStage": "INITIAL",
    "documents": {
      "pan": [
        {
          "documentId": "doc-1",
          "documentName": "pan-card",
          "documentUrl": "https://example.com/pan.pdf",
          "documentType": "PAN"
        }
      ]
    },
    "transactionId": "txn-123",
    "kycId": "kyc-123",
    "paymentId": "payment-123",
    "cityList": [
      {
        "cityCode": "280",
        "cityName": "Pune"
      }
    ],
    "areaCode": "AREA1",
    "area": "Kothrud",
    "remarks": "sample remarks",
    "timestamp": "2026-03-30T12:00:00+05:30",
    "memberTypeCode": "MT1",
    "insurerOrderNo": "INS-ORD-1",
    "tpClientRefNo": "TPREF123",
    "panIndiaCover": false,
    "standingInstruction": false,
    "voluntaryCoPay": "0",
    "coverType": "FAMILY_FLOATER",
    "isSharedWithCustomer": false,
    "isCustomerUpdated": false,
    "lastUpdatedBy": "customer",
    "cignaAddons": {},
    "addOns": {
      "hospital_cash": {
        "code": "hospital_cash",
        "name": "Hospital Cash",
        "selected": false
      }
    },
    "dependants": [],
    "proposerPremium": {
      "memberCode": "SELF",
      "premium": 12456
    },
    "kycInfo": {
      "ckycNumber": "123456789012"
    },
    "isRuleEngineInvocationRequired": false,
    "isRepremiumCallCompleted": false,
    "initialPremiumAmount": "12456",
    "nivaRuleEngineApplicationResult": "",
    "ruleEngineResults": {},
    "kycReferenceId": "KYCREF123",
    "permanentAddress": {
      "address1": "Flat 101",
      "address2": "ABC Residency",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041"
    },
    "uploadedFormType": "CKYC",
    "kycType": "CKYC",
    "panNotAvailable": false,
    "isFormUploadedAtKyc": false,
    "quotesPerRequest": 3,
    "portabilityCheckoutDetails": {
      "previousInsurer": "ABC Health"
    },
    "claimRaised": false,
    "portabilityClaimsDetails": [],
    "nivabupaRuleEngineLink": "",
    "nivabupaLoadingLetterLink": "",
    "healthOpsIssuance": false,
    "preExistingDisease": false,
    "productKey": "all_members$care-health",
    "salesProJourneyStatus": "CHECKOUT_DETAILS_SHARED_TO_RM",
    "proposerBankDetails": {
      "accountHolderName": "asdasd",
      "accountNumber": "1234567890",
      "ifscCode": "HDFC0001234"
    },
    "proposalConsent": true
  },
  "meta": {
    "status": "SUCCESS",
    "error": false
  }
}
```

## POST Checkout Response

```json
{
  "data": {
    "_id": "PR-H-1",
    "proposalResultId": "PR-H-1",
    "referenceId": "AHW41N05KP9",
    "premiumResultId": "RID-H-1",
    "insurerCode": "CARE",
    "productCode": "health",
    "provider": "CARE",
    "partnerId": "partner-id",
    "tenant": "tm",
    "broker": "tm",
    "userId": "user-id",
    "leadName": "asdasd",
    "businessType": "NEW",
    "policyTerm": 1,
    "proposalUrl": "",
    "statusCode": "SUCCESS",
    "statusMessage": "Checkout saved successfully",
    "proposalStatus": "CHECKOUT_SAVED",
    "stage": "INITIAL",
    "selectedBucketName": "all_members",
    "quoteId": "QID-H-1",
    "pricingRequestId": "AHW41N05KP9",
    "productId": "care-supreme",
    "productKey": "all_members$care-health",
    "planCode": "care-supreme",
    "planName": "Care Supreme",
    "planType": "BASIC",
    "premiumAmount": "12456",
    "basePremiumAmount": "10556",
    "grossPremium": "12456",
    "taxAmount": "1900",
    "serviceTax": 1900,
    "coverAmount": "1000000",
    "deductible": "0",
    "sumInsured": 1000000,
    "noOfAdults": 4,
    "noOfChildren": 1,
    "pincode": 411041,
    "city": "Pune",
    "state": "Maharashtra",
    "status": "INITIATED",
    "proposalOnline": true,
    "preExistingDisease": false,
    "proposalConsent": true,
    "insuredMembers": [
      {
        "insuredFullName": "asdasd",
        "type": "self",
        "usertype": "SELF",
        "gender": "M",
        "age": 24,
        "age_months": 288,
        "dateOfBirth": "2002-03-30T00:00:00+05:30",
        "pincode": "411041",
        "hospitalIds": [],
        "ped": {
          "hypertension": false,
          "diabetes": false,
          "heartDiseases": false,
          "asthma": false,
          "obesity": false,
          "otherCondition": false,
          "otherConditionText": ""
        }
      }
    ],
    "proposer": {
      "insuredFullName": "asdasd",
      "type": "self",
      "usertype": "SELF",
      "gender": "M",
      "age": 24,
      "age_months": 288,
      "dateOfBirth": "2002-03-30T00:00:00+05:30",
      "pincode": "411041",
      "hospitalIds": [],
      "ped": {
        "hypertension": false,
        "diabetes": false,
        "heartDiseases": false,
        "asthma": false,
        "obesity": false,
        "otherCondition": false,
        "otherConditionText": ""
      }
    },
    "medicalHistory": {
      "ped_questionnaire": {
        "code": "ped_questionnaire",
        "question": "Any PED?",
        "answer": "No",
        "members": {}
      }
    },
    "documents": {
      "pan": [
        {
          "documentId": "doc-1",
          "documentName": "pan-card",
          "documentUrl": "https://example.com/pan.pdf",
          "documentType": "PAN"
        }
      ]
    },
    "kycId": "kyc-123",
    "paymentId": "payment-123",
    "transactionId": "txn-123",
    "transactionSource": "API",
    "transactionMode": "ONLINE",
    "personalDetails": {
      "customerName": "asdasd",
      "userMobile": "7400400747",
      "userEmail": "shahabid37@gmail.com"
    },
    "registeredAddress": {
      "addressLine1": "Flat 101",
      "addressLine2": "ABC Residency",
      "addressLine3": "Near Metro",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041"
    }
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "2026-03-30T12:00:00"
  }
}
```

## Notes

- `stage` stays inside `data`
- all health checkout params are kept directly inside `data`
- `ped` is member disease state
- `medicalHistory` is questionnaire and insurer checkout structure

## GET Checkout Payloads

API:
- `GET /api/minterprise/v2/products/health/checkout?referenceId=AHW41N05KP9&selectedBucketName=all_members`

### GET Request

GET has no body. FE should send query params:

```json
{
  "referenceId": "AHW41N05KP9",
  "selectedBucketName": "all_members"
}
```

### GET Response

```json
{
  "data": {
    "_id": "PR-H-1",
    "proposalResultId": "PR-H-1",
    "referenceId": "AHW41N05KP9",
    "premiumResultId": "RID-H-1",
    "insurerCode": "CARE",
    "productCode": "health",
    "provider": "CARE",
    "partnerId": "partner-id",
    "tenant": "tm",
    "broker": "tm",
    "userId": "user-id",
    "partnerOrderId": "partner-order-id",
    "leadName": "asdasd",
    "businessType": "NEW",
    "policyTerm": 1,
    "proposalUrl": "",
    "statusCode": "SUCCESS",
    "statusMessage": "Checkout fetched successfully",
    "proposalStatus": "CHECKOUT_SAVED",
    "stage": "INITIAL",
    "selectedBucketName": "all_members",
    "quoteId": "QID-H-1",
    "pricingRequestId": "AHW41N05KP9",
    "productId": "care-supreme",
    "productKey": "all_members$care-health",
    "planCode": "care-supreme",
    "planName": "Care Supreme",
    "planType": "BASIC",
    "premiumAmount": "12456",
    "basePremiumAmount": "10556",
    "grossPremium": "12456",
    "taxAmount": "1900",
    "serviceTax": 1900,
    "coverAmount": "1000000",
    "deductible": "0",
    "sumInsured": 1000000,
    "noOfAdults": 4,
    "noOfChildren": 1,
    "pincode": 411041,
    "city": "Pune",
    "state": "Maharashtra",
    "status": "INITIATED",
    "proposalOnline": true,
    "preExistingDisease": false,
    "proposalConsent": true,
    "paymentLinkExpired": false,
    "errorMessage": null,
    "insuredMembers": [
      {
        "insuredFullName": "asdasd",
        "type": "self",
        "usertype": "SELF",
        "gender": "M",
        "age": 24,
        "age_months": 288,
        "dateOfBirth": "2002-03-30T00:00:00+05:30",
        "pincode": "411041",
        "hospitalIds": [],
        "ped": {
          "hypertension": false,
          "diabetes": false,
          "heartDiseases": false,
          "asthma": false,
          "obesity": false,
          "otherCondition": false,
          "otherConditionText": ""
        }
      }
    ],
    "proposer": {
      "insuredFullName": "asdasd",
      "type": "self",
      "usertype": "SELF",
      "gender": "M",
      "age": 24,
      "age_months": 288,
      "dateOfBirth": "2002-03-30T00:00:00+05:30",
      "pincode": "411041",
      "hospitalIds": [],
      "ped": {
        "hypertension": false,
        "diabetes": false,
        "heartDiseases": false,
        "asthma": false,
        "obesity": false,
        "otherCondition": false,
        "otherConditionText": ""
      }
    },
    "medicalHistory": {
      "ped_questionnaire": {
        "code": "ped_questionnaire",
        "question": "Any PED?",
        "answer": "No",
        "members": {}
      }
    },
    "documents": {
      "pan": [
        {
          "documentId": "doc-1",
          "documentName": "pan-card",
          "documentUrl": "https://example.com/pan.pdf",
          "documentType": "PAN"
        }
      ]
    },
    "kycId": "kyc-123",
    "paymentId": "payment-123",
    "transactionId": "txn-123",
    "transactionSource": "API",
    "transactionMode": "ONLINE",
    "personalDetails": {
      "customerName": "asdasd",
      "userMobile": "7400400747",
      "userEmail": "shahabid37@gmail.com"
    },
    "registeredAddress": {
      "addressLine1": "Flat 101",
      "addressLine2": "ABC Residency",
      "addressLine3": "Near Metro",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041"
    },
    "pricingRequest": {
      "pricingRequestId": "AHW41N05KP9",
      "businessType": "NEW",
      "coverAmount": 1000000,
      "coverType": "FAMILY_FLOATER",
      "deductible": 0,
      "selectedBucketName": "all_members",
      "noOfAdults": 4,
      "noOfChildren": 1,
      "pincode": [
        "411041"
      ],
      "preExistingDisease": false,
      "requireMaternity": false,
      "insuredMembers": [
        {
          "type": "self",
          "usertype": "SELF",
          "gender": "M",
          "age": 24,
          "age_months": 288,
          "pincode": "411041"
        }
      ],
      "buckets": [
        {
          "bucketName": "all_members",
          "uniqueId": "dfafb1ef-82cf-4d4e-bc0c-1804143ff0f0",
          "sumInsured": 1000000,
          "deductible": 0,
          "coverType": "FAMILY_FLOATER",
          "noOfAdults": 4,
          "noOfChildren": 1,
          "pincode": "411041",
          "city": "Pune",
          "state": "Maharashtra"
        }
      ]
    }
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "2026-03-30T15:00:00"
  }
}
```

## Supporting APIs

### 1. KYC Checkout Info

API:
- `GET /api/minterprise/v2/products/health/kyc/checkout-info?insurerCode=CARE&kycType=CKYC`

#### Request

GET has no body. FE should send query params:

```json
{
  "insurerCode": "CARE",
  "kycType": "CKYC"
}
```

#### Response

```json
{
  "data": [
    {
      "insurerCode": "CARE",
      "kycType": "CKYC",
      "status": true,
      "config": [
        {
          "proposer": {
            "name": "nonEditable",
            "dob": "nonEditable",
            "panNo": "nonEditable"
          },
          "elements": [
            {
              "slide": "PROPOSER",
              "section": "PERSONAL_DETAILS",
              "field": "dob",
              "action": "nonEditable"
            },
            {
              "slide": "PROPOSER",
              "section": "KYC_DETAILS",
              "field": "panNo",
              "action": "nonEditable"
            }
          ]
        }
      ]
    }
  ],
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "2026-03-30T16:00:00"
  }
}
```

### 2. STAR City Details

API:
- `GET /api/minterprise/v2/products/health/star/city-details?productId=SC&pinCode=411041`

#### Request

GET has no body. FE should send query params:

```json
{
  "productId": "SC",
  "pinCode": "411041"
}
```

#### Response

```json
{
  "data": {
    "city": [
      {
        "city_id": "280",
        "city_name": "Pune"
      }
    ]
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "2026-03-30T16:00:00"
  }
}
```

### 3. STAR Area Details

API:
- `GET /api/minterprise/v2/products/health/star/area-details?productId=SC&pinCode=411041&city_id=280`

#### Request

GET has no body. FE should send query params:

```json
{
  "productId": "SC",
  "pinCode": "411041",
  "city_id": "280"
}
```

#### Response

```json
{
  "data": {
    "area": [
      {
        "areaID": "A1",
        "areaName": "Kothrud",
        "areaClassification": "Urban"
      }
    ]
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "2026-03-30T16:00:00"
  }
}
```

### 4. Payment Modes

Legacy API:
- `GET /api/health/getpaymentmodes?planId=care-supreme&insurer=CARE`

API:
- `GET /api/minterprise/v2/products/health/payment-modes?planId=care-supreme&insurerCode=CARE`

#### Request

GET has no body. FE should send query params:

```json
{
  "planId": "care-supreme",
  "insurerCode": "CARE"
}
```

#### Response

```json
{
  "data": {
    "paymentModes": {
      "ONLINE": {
        "enabled": true,
        "displayName": "Online"
      },
      "CHEQUE": {
        "enabled": false,
        "displayName": "Cheque"
      }
    }
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "2026-03-30T16:30:00"
  }
}
```

### 5. Checkout Rules Evaluate

Legacy API:
- `POST /api/health/rules/evaluate`

API:
- `POST /api/minterprise/v2/products/health/checkout/rules/evaluate`

#### Request

```json
{
  "data": {
    "facts": {
      "insurerCode": "CARE",
      "productId": "care-supreme",
      "selectedBucketName": "all_members",
      "coverAmount": 1000000,
      "deductible": 0,
      "noOfAdults": 4,
      "noOfChildren": 1,
      "businessType": "NEW",
      "policyTerm": 1,
      "preExistingDisease": false,
      "payMode": "ONLINE"
    }
  },
  "meta": {
    "status": "SUCCESS",
    "error": false
  }
}
```

#### Response

```json
{
  "data": {
    "isValid": true,
    "rules": [],
    "message": "SUCCESS"
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "2026-03-30T16:30:00"
  }
}
```

### 6. Send Proposal

Legacy API:
- `POST /api/health/sendproposal`

Minterprise status:
- already covered by existing minterprise proposal flow

Existing minterprise API:
- `POST /api/minterprise/v2/products/health/proposals`

#### Request

```json
{
  "data": {
    "referenceId": "AHW41N05KP9",
    "premiumResultId": "RID-H-1",
    "insurerCode": "CARE",
    "productCode": "health",
    "leadName": "asdasd",
    "businessType": "NEW",
    "policyTerm": 1,
    "payMode": "ONLINE",
    "personalDetails": {
      "customerName": "asdasd",
      "userMobile": "7400400747",
      "userEmail": "asdasd@gmail.com"
    },
    "registeredAddress": {
      "addressLine1": "Flat 101",
      "addressLine2": "ABC Residency",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041"
    },
    "selectedBucketName": "all_members",
    "pricingRequestId": "AHW41N05KP9",
    "quoteId": "QID-H-1",
    "productId": "care-supreme",
    "productKey": "all_members$care-health",
    "planCode": "care-supreme",
    "planName": "Care Supreme",
    "planType": "BASIC",
    "premiumAmount": "12456",
    "coverAmount": "1000000",
    "deductible": "0",
    "insuredMembers": [
      {
        "insuredFullName": "asdasd",
        "type": "self",
        "usertype": "SELF",
        "gender": "M",
        "age": 24,
        "age_months": 288,
        "pincode": "411041"
      }
    ],
    "proposer": {
      "insuredFullName": "asdasd",
      "type": "self",
      "usertype": "SELF",
      "gender": "M",
      "age": 24,
      "age_months": 288,
      "pincode": "411041"
    },
    "medicalHistory": {
      "ped_questionnaire": {
        "code": "ped_questionnaire",
        "question": "Any PED?",
        "answer": "No",
        "members": {}
      }
    },
    "documents": {},
    "proposalConsent": true
  },
  "meta": {
    "status": "SUCCESS",
    "error": false
  }
}
```

#### Response

```json
{
  "data": {
    "_id": "PR-H-1",
    "proposalResultId": "PR-H-1",
    "referenceId": "AHW41N05KP9",
    "premiumResultId": "RID-H-1",
    "insurerCode": "CARE",
    "productCode": "health",
    "proposalId": "INS-PROP-123",
    "insurerProposalId": "INS-PROP-123",
    "leadName": "asdasd",
    "businessType": "NEW",
    "policyTerm": 1,
    "statusCode": "SUCCESS",
    "statusMessage": "Proposal submitted successfully",
    "proposalStatus": "PROPOSAL_SUBMITTED",
    "proposalUrl": "https://example.com/proposal/AHW41N05KP9",
    "transactionSource": "API",
    "transactionMode": "ONLINE"
  },
  "meta": {
    "status": "SUCCESS",
    "error": false,
    "traceId": "...",
    "timestamp": "2026-03-30T16:30:00"
  }
}
```

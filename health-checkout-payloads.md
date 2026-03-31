# Health Proposal and Checkout API Payloads

This document captures the FE payload contracts for health proposal and checkout-related APIs in minterprise.

## Wrapper

All POST APIs use the standard minterprise wrapper:

```json
{
  "data": {},
  "meta": {}
}
```

GET APIs use query params and return the standard response wrapper.

## 1. POST Proposal / Checkout Save

API:

- `POST /api/minterprise/v2/products/health/proposals`

Behavior:

- `sendProposal: false` saves or updates checkout data
- `sendProposal: true` submits the proposal

### Request

```json
{
  "data": {
    "quoteId": "QID-H-1",
    "referenceId": "AHW41N05KP9",
    "premiumResultId": "RID-H-1",
    "insurerCode": "CARE",
    "productCode": "health",
    "productId": "care-supreme",
    "internalProductCode": "care-health-care-supreme",
    "sendProposal": false,
    "leadName": "asdasd",
    "businessType": "NEW",
    "policyTerm": 1,
    "tenant": "axisbank",
    "broker": "axisbank",
    "partnerId": "647f458828effa0001044980",
    "personalDetails": {
      "title": "MR",
      "firstName": "asdasd",
      "lastName": "test",
      "dob": "2002-03-30T00:00:00+05:30",
      "gender": "MALE",
      "mobile": "7400400747",
      "email": "asdasd@gmail.com",
      "pan": "ABCDE1234F",
      "maritalStatus": "Married",
      "qualification": "Masters & above",
      "occupation": "Business",
      "age": 24,
      "pincode": "411041",
      "age_months": 288,
      "income": "699999"
    },
    "registeredAddress": {
      "address1": "Flat 101, Shree Residency",
      "address2": "Baner Road",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041",
      "country": "India"
    },
    "communicationAddress": {
      "address1": "Flat 101, Shree Residency",
      "address2": "Baner Road",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041",
      "country": "India"
    },
    "nomineeDetails": [
      {
        "title": "MRS",
        "firstName": "Jane",
        "lastName": "Doe",
        "dob": "2004-01-27T00:00:00+05:30",
        "relationship": "Spouse",
        "gender": "F",
        "mobile": 9167888888
      }
    ],
    "insuredMembers": [
      {
        "title": "MR",
        "gender": "M",
        "firstName": "asdasd",
        "lastName": "test",
        "dob": "2002-03-30T00:00:00+05:30",
        "mobile": 7400400747,
        "email": "asdasd@gmail.com",
        "type": "self",
        "usertype": "SELF",
        "age": 24,
        "age_months": 288,
        "pincode": "411041",
        "occupation": "Business",
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
      {
        "title": "MRS",
        "gender": "F",
        "firstName": "spouse",
        "lastName": "test",
        "dob": "2002-03-30T00:00:00+05:30",
        "type": "spouse",
        "usertype": "SPOUSE",
        "age": 24,
        "age_months": 288,
        "pincode": "411041",
        "occupation": "Business",
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
    "otherDetails": {
      "paymentDetails": {
        "payMode": "ONLINE"
      },
      "insurerSpecificInfo": {
        "proposalOnline": true,
        "preExistingDisease": false,
        "cityCode": "280",
        "stateCode": "14",
        "pincodeZone": 2,
        "voluntaryCoPay": "0",
        "areaCode": "AREA1",
        "area": "Kothrud",
        "panIndiaCover": false,
        "standingInstruction": false,
      },
      "premiumDetails": {
        "premiumAmount": "12456",
        "basePremiumAmount": "10556",
        "grossPremium": 12456,
        "taxAmount": "1900",
        "totalPremiumDbl": 12456,
        "initialPremiumAmount": "12456"
      },
      "checkoutInfo": {
        "stage": "INITIAL",
        "status": "INITIATED",
        "healthSpecificData": {
          "coverAmount": "1000000",
          "sumInsured": 1000000,
          "deductible": "0",
          "coverType": "FAMILY_FLOATER",
          "noOfAdults": 4,
          "noOfChildren": 1,
          "selectedBucketName": "all_members",
          "medicalHistory": {
            "ped_questionnaire": {
              "code": "ped_questionnaire",
              "question": "Any PED?",
              "answer": "No",
              "members": {}
            }
          }
        },
        "addOns": {
          "hospital_cash": {
            "code": "hospital_cash",
            "name": "Hospital Cash",
            "selected": false
          }
        },
        "productKey": "all_members$care-health",
        "planCode": "care-supreme",
        "planName": "Care Supreme",
        "planType": "BASIC",
        "insurerName": "Care Health",
        "kycTransactionId": "txn-123",
        "timestamp": "2026-03-30T12:00:00+05:30",
        "isRepremiumCallCompleted": false,
        "proposalConsent": true
      }
    }
  },
  "meta": {
    "status": "SUCCESS",
    "error": false
  }
}
```

### Response When `sendProposal=false`

```json
{
  "data": {
    "quoteId": "QID-H-1",
    "referenceId": "AHW41N05KP9",
    "premiumResultId": "RID-H-1",
    "insurerCode": "CARE",
    "productCode": "health",
    "productId": "care-supreme",
    "internalProductCode": "care-health-care-supreme",
    "sendProposal": false,
    "leadName": "asdasd",
    "businessType": "NEW",
    "policyTerm": 1,
    "tenant": "axisbank",
    "broker": "axisbank",
    "partnerId": "647f458828effa0001044980",
    "personalDetails": {
      "title": "MR",
      "firstName": "asdasd",
      "lastName": "test",
      "dob": "2002-03-30T00:00:00+05:30",
      "gender": "MALE",
      "mobile": "7400400747",
      "email": "asdasd@gmail.com",
      "pan": "ABCDE1234F",
      "maritalStatus": "Married",
      "qualification": "Masters & above",
      "occupation": "Business",
      "age": 24,
      "pincode": "411041",
      "age_months": 288,
      "income": "699999"
    },
    "registeredAddress": {
      "address1": "Flat 101, Shree Residency",
      "address2": "Baner Road",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041",
      "country": "India"
    },
    "communicationAddress": {
      "address1": "Flat 101, Shree Residency",
      "address2": "Baner Road",
      "city": "Pune",
      "state": "Maharashtra",
      "pincode": "411041",
      "country": "India"
    },
    "nomineeDetails": [
      {
        "title": "MRS",
        "firstName": "Jane",
        "lastName": "Doe",
        "dob": "2004-01-27T00:00:00+05:30",
        "relationship": "Spouse",
        "gender": "F",
        "mobile": 9167888888
      }
    ],
    "insuredMembers": [
      {
        "title": "MR",
        "gender": "M",
        "firstName": "asdasd",
        "lastName": "test",
        "dob": "2002-03-30T00:00:00+05:30",
        "mobile": 7400400747,
        "email": "asdasd@gmail.com",
        "type": "self",
        "usertype": "SELF",
        "age": 24,
        "age_months": 288,
        "pincode": "411041",
        "occupation": "Business",
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
      {
        "title": "MRS",
        "gender": "F",
        "firstName": "spouse",
        "lastName": "test",
        "dob": "2002-03-30T00:00:00+05:30",
        "type": "spouse",
        "usertype": "SPOUSE",
        "age": 24,
        "age_months": 288,
        "pincode": "411041",
        "occupation": "Business",
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
    "otherDetails": {
      "paymentDetails": {
        "payMode": "ONLINE"
      },
      "insurerSpecificInfo": {
        "proposalOnline": true,
        "preExistingDisease": false,
        "cityCode": "280",
        "stateCode": "14",
        "pincodeZone": 2,
        "voluntaryCoPay": "0",
        "areaCode": "AREA1",
        "area": "Kothrud",
        "panIndiaCover": false,
        "standingInstruction": false,
      },
      "premiumDetails": {
        "premiumAmount": "12456",
        "basePremiumAmount": "10556",
        "grossPremium": 12456,
        "taxAmount": "1900",
        "totalPremiumDbl": 12456,
        "initialPremiumAmount": "12456"
      },
      "checkoutInfo": {
        "stage": "INITIAL",
        "status": "INITIATED",
        "healthSpecificData": {
          "coverAmount": "1000000",
          "sumInsured": 1000000,
          "deductible": "0",
          "coverType": "FAMILY_FLOATER",
          "noOfAdults": 4,
          "noOfChildren": 1,
          "selectedBucketName": "all_members",
          "medicalHistory": {
            "ped_questionnaire": {
              "code": "ped_questionnaire",
              "question": "Any PED?",
              "answer": "No",
              "members": {}
            }
          }
        },
        "addOns": {
          "hospital_cash": {
            "code": "hospital_cash",
            "name": "Hospital Cash",
            "selected": false
          }
        },
        "productKey": "all_members$care-health",
        "planCode": "care-supreme",
        "planName": "Care Supreme",
        "planType": "BASIC",
        "insurerName": "Care Health",
        "kycTransactionId": "txn-123",
        "timestamp": "2026-03-30T12:00:00+05:30",
        "isRepremiumCallCompleted": false,
        "proposalConsent": true
      }
    }
  },
  "meta": {
    "status": "SUCCESS",
    "error": false
  }
}
```

## 2. GET Checkout

API:

- `GET /api/minterprise/v2/products/health/checkout?referenceId=AHW41N05KP9&selectedBucketName=all_members`

### Request

GET has no body. FE should send query params:

```json
same as post response
```

## 3. KYC Checkout Info

API:

- `GET /api/minterprise/v2/products/health/kyc/checkout-info?insurerCode=CARE&kycType=CKYC`

### Request

GET has no body. FE should send query params:

```json
{
  "insurerCode": "CARE",
  "kycType": "CKYC"
}
```

### Response

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

## 4. STAR City Details

API:

- `GET /api/minterprise/v2/products/health/star/city-details?productId=SC&pinCode=411041`

### Request

GET has no body. FE should send query params:

```json
{
  "productId": "SC",
  "pinCode": "411041"
}
```

### Response

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

## 5. STAR Area Details

API:

- `GET /api/minterprise/v2/products/health/star/area-details?productId=SC&pinCode=411041&city_id=280`

### Request

GET has no body. FE should send query params:

```json
{
  "productId": "SC",
  "pinCode": "411041",
  "city_id": "280"
}
```

### Response

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

## 6. Payment Modes

API:

- `GET /api/minterprise/v2/products/health/payment-modes?planId=care-supreme&insurerCode=CARE`

### Request

GET has no body. FE should send query params:

```json
{
  "planId": "care-supreme",
  "insurerCode": "CARE"
}
```

### Response

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

## 7. Checkout Rules Evaluate

API:

- `POST /api/minterprise/v2/products/health/checkout/rules/evaluate`

### Request

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

### Response

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

## API Specification: Get Clinics
> Description: This API fetches a list of clinics associated with a specified establishment code.

### HTTP Method
- GET

### Endpoint
``` QA: {baseurl}/nehrapi/gup/getClinics ```
- eg: ``` {baseurl}/getClinics?estCode=20068 ```

###  Query Parameters
- estCode: 20068 - The establishment code for which clinic details are requested.
### Headers
- Authorization: Bearer [Token] - The Bearer token required for authentication.
### Successful Response
- HTTP Status Code: 200 (OK)

### Content-Type: application/json

### Body:

```
{
    "version": "v2",
    "code": 0,
    "message": "3 Records found",
    "result": [
        {
            "doctDeptId": 499,
            "doctDeptName": "R1-Gen Practice",
            "spClinic": 601,
            "unitId": 236,
            "type": "B",
            "divCode": 530,
            "divName": "GENERAL MEDICINE",
            "earliestDate": 1716408000000
        },
        {
            "doctDeptId": 473,
            "doctDeptName": "General Medicine Virtual Clinic",
            "doctdeptnameNl": "الطب العام الافتراضي",
            "spClinic": 601,
            "unitId": 236,
            "type": "B",
            "divCode": 530,
            "divName": "GENERAL MEDICINE",
            "earliestDate": 1716408000000
        },
        {
            "doctDeptId": 489,
            "doctDeptName": "HEALTH EDUCATION",
            "spClinic": 12059,
            "unitId": 245,
            "type": "B",
            "divCode": 26039,
            "divName": "HEALTH PROMOTION",
            "divNameNls": "تعزيز الصحة",
            "earliestDate": 1716408000000
        }
    ]
}
```
### Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result (array): An array of clinic details.
  - doctDeptId (integer): Department ID of the clinic.
  - doctDeptName (string): Name of the department.
  - doctdeptnameNl (string): Localized name of the department.
  - spClinic (integer): Special clinic ID.
  - unitId (integer): Unit ID of the clinic.
  - type (string): Type of the clinic.
  - noOverBook (object): Information about overbooking capability.
  - divCode (integer): Division code.
  - divName (string): Name of the division.
  - divNameNls (string): Localized name of the division.
  - earliestDate (integer): Earliest available date timestamp.
## Error/other Responses

### Invalid est code
- HTTP Status Code: 200 (OK)
#### Content-Type: application/json
##### Body:

```
{
    "version": "v2",
    "code": 3,
    "message": "Invalid est code",
    "result": null
}
```

### Invalid Tocken
- HTTP Status Code: 401 (Unauthorized)
#### Content-Type: application/json
##### Body:
```
{
    "error": "invalid_token",
    "error_description": "d0816a77-af67-43fc-bad1-2edb2aa222e3dc5"
}
```

This document provides a comprehensive guide for developers to understand and integrate with the API endpoint to fetch details of clinics associated with a specific establishment code.

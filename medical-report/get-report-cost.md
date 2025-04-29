## API Specification: Get Institutes for Patient
> Description: This API retrieves cost of the report for a given patient  and the report type

### HTTP Method
- POST

### Endpoint
 ``` {BASEURL}/report/cost ```



### Headers
- Authorization: Bearer d0816a77-af67-43fc-bad1-2edb2aae3dc5 - The Bearer token required for authentication.
### Request Body
```
{
  "civilId": 20134401
  "estCode" : 3453,
  "patientId": 34401
  "reportType": 23
}
```
### Parameters:
- civilId (integer): The civil ID of the patient.
- estCode : the establishment code/ hospital code
- patientId: Patient Id of given estCode
- reportType: the type of the report
#### Successful Response
- HTTP Status Code: 200 (OK)

### Content-Type: application/json

## Body:

```
{
    "version": "v2",
    "code": 0,
    "message": "1 Records found",
    "result": [
        {
            "patientId": 2704847,
            "estCode":   20068,
            "reportType": 2,
            "cost": 6.000,
        }
    ]
}
```
## Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result : the cost the medical report (single record)
  - estCode (string): Establishment code.
  - estPatientId (integer): Establishment's patient ID.
  

### Error/Other Responses

### 1. Invalit Token/Unauthorized
 -  HTTP Status Code: 401 (Unauthorized)
#### Content-Type: application/json
#### Body:
```
{
    "error": "invalid_token",
    "error_description": "d0816a77-af67-43fc-bad1-2edb2aae3dc51"
}
```



> This document serves as a comprehensive guide for developers to understand how to integrate and troubleshoot interactions with this specific API endpoint.

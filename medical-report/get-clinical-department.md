## API Specification: Get Clinical Departments for a Specific Establishment
> Description: This API retrieves the list of clinical departments for a given establishment based on its establishment code (estCode).

### HTTP Method
- POST

### Endpoint
 ``` {BASEURL}/v2/getClinicalDepartments ```

### Headers
- Authorization: Bearer d0816a77-af67-43fc-bad1-2edb2aae3dc5 - The Bearer token required for authentication.
### Request Body
```
{
  "estCode": 20068
}
```
### Parameters:
- estCode (integer): The establishment code for which the clinical department list is to be retrieved.
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
            "estCode": 20068,
            "deptCode": 101,
            "deptName": "Cardiology",
            "deptType": 1,
            "divCode": 10,
            "activeYn": "Y",
            "deptHead": 1001,
            "deptTelDirect": 1234567890,
            "deptTelExtn": 202,
            "deptFax": 1234567891,
            "emailId": "cardiology@example.com",
            "admissionAllowedYn": "Y"
        }
    ]
}
```
## Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result (array): Array of clinical department details.
  - estCode (integer): Establishment code.
  - deptCode (integer): Department code.
  - deptName (string): Name of the department.
  - deptType (integer): Type of department.
  - divCode (integer): Division code.
  - activeYn (string): Indicates if the department is active ('Y' for yes).
  - deptHead (integer): Department head ID.
  - deptTelDirect (integer): Direct telephone number of the department.
  - deptTelExtn (integer): Telephone extension of the department.
  - deptFax (integer): Fax number of the department.
  - emailId (string): Email address of the department.
  - admissionAllowedYn (string): Indicates if admissions are allowed ('Y' for yes).

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

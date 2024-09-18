## API Specification: Retrieve all Clinical Report Types
> Description: This API retrieves the list of clinical report types.

### HTTP Method
- GET

### Endpoint
 ``` {BASEURL}/v2/getMedicalReportTypes ```

### Headers
- Authorization: Bearer d0816a77-af67-43fc-bad1-2edb2aae3dc5 - The Bearer token required for authentication.


#### Successful Response
- HTTP Status Code: 200 (OK)

### Content-Type: application/json

## Body:

```
{
    "version": "v2",
    "code": 0,
    "message": "5 Records found",
   "result": [
    {
      "reportTypeId": 72,
      "reportName": "Medical Report",
      "cost": 5
    },
    {
      "reportTypeId": 75,
      "reportName": "Medical Report - Dental,Oral & Maxillofacial Surgeryt",
      "cost": 5
    },
    {
      "reportTypeId": 12347,
      "reportName": "Medical Report - Renal",
      "cost": 5
    }
    // ... additional records
  ]
    ]
}

```
## Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result (array): Array of valid reasons for requesting a clinical report.
  - reportTypeId (integer): Unique identifier for the report type.
  - reportName (string): Name of the clinical report.
  - cost (integer): Cost of the clinical report.


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

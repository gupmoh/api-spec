## API Specification: Retrieve Valid Reasons for Requesting a Clinical Report
> Description: This API retrieves the list of valid reasons from the CLINICAL_REPORT_REQUEST_REASON table for requesting a clinical report.

### HTTP Method
- GET

### Endpoint
 ``` {BASEURL}/v2/getReportRequestReasons ```

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
            "id": 101,
            "value": "Follow-up visit"
        },
        {
            "id": 102,
            "value": "Second opinion"
        },
        {
            "id": 103,
            "value": "Medical transfer"
        },
        {
            "id": 104,
            "value": "Insurance claim"
        },
        {
            "id": 105,
            "value": "Other"
        }
    ]
}

```
## Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result (array): Array of valid reasons for requesting a clinical report.
  - id (integer): Unique identifier for the request reason.
  - value (string): Description or value of the request reason.


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

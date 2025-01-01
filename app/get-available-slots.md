## API Specification: Get Available Slots
> Description: This API retrieves available appointment slots for a specified clinic, given the patient's civil ID and the clinic's details.

### HTTP Method
- POST

### Endpoint
``` {baseurl}/getSlots ```

### Request Body
```
{
  "civilId": 20134401,
  "clinicId": 499,
  "estCode": 20068,
  "fromDate": "2024-05-01 12:00:00",
  "toDate": "2024-05-30 12:00:00"
}
```
### Parameters:

- civilId (integer): The civil ID of the patient.
- clinicId (integer): The ID of the clinic.
- estCode (string): Establishment code of the clinic.
- fromDate (string): Start date and time from when the slots are needed (format: YYYY-MM-DD HH:MM:SS).
- toDate (string): End date and time until when the slots are needed (format: YYYY-MM-DD HH:MM:SS).

### Headers
- Authorization: Bearer [Token] - The Bearer token required for authentication.
### Successful Response
- HTTP Status Code: 200 (OK)
- 

#### Content-Type: application/json

##### Body:

```
{
    "version": "v2",
    "code": 0,
    "message": "1 Records found",
    "result": {
        "patientId": 54124,
        "slots": [
            {
                "noOfDays": 29,
                "runId": 823884,
                "deptId": 37,
                "appTimeStamp": 1716436800000,
                "appointmentDate": "23-May-2024",
                "timeBlock": "08:00",
                "clinicId": 499,
                "clinicName": "R1-Gen Practice",
                "deptName": "General Medicine (NG)",
                "deptNameNls": "الطب العام",
                "divCode": 530,
                "divName": "GENERAL MEDICINE"
            }
            // Additional slots are omitted for brevity.
        ]
    }
}
```
### Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result (object): Contains the patient ID and an array of available slots.
    - patientId (integer): ID of the patient.
    - slots (array): List of available slots.
    - noOfDays (integer): Number of days from the fromDate to the slot's appointment date.
    - runId (integer): Unique identifier for the appointment run.
    - deptId (integer): Department ID.
    - appTimeStamp (integer): Timestamp of the appointment.
    - appointmentDate (string): Date of the appointment.
    - timeBlock (string): Time block of the appointment.
    - clinicId (integer): ID of the clinic.
    - clinicName (string): Name of the clinic.
    - deptName (string): Name of the department.
    - deptNameNls (string): Localized name of the department.
    - divCode (integer): Division code.
    - divName (string): Name of the division.
    - divNameNls (string): Localized name of the division.
#### Error Responses

1. ###  Invalid token/Unauthorized
- HTTP Status Code: 401 (Unauthorized)
#### Content-Type: application/json
##### Body:
```
{
    "error": "invalid_token",
    "error_description": "d0816a77-af67-43fc-bad1-2edb2aae3dc51"
}
```


2. ### no-record-found
- HTTP Status Code: 200 (OK)
#### Content-Type: application/json
##### Body:
````
{
    "version": "v2",
    "code": 4,
    "message": "No Record Found",
    "result": null
}
````

> This document provides a comprehensive guide for developers to understand and integrate with the API endpoint to fetch available appointment slots for specified clinics.

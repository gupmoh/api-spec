## API Specification: Get Appointment Details
> Description: This API fetches the future appointment details for a specified patient based on their civil ID.

### HTTP Method
- POST

### Endpoint
``` {baseurl}/v2/appointment ```

```
{
  "civilId": 64891745
}

```

### Headers
- Authorization: Bearer [Token] - The Bearer token required for authentication.

### Successful Response
``` HTTP Status Code: 200 (OK) ```

#### Content-Type: application/json

##### Body:
```
{
    "version": "v2",
    "code": 0,
    "message": "1 Records found",
    "result": [
        {
            "id": "3.20068.523067",
            "profileCode": 3,
            "lastModifiedBy": 20068,
            "lastModifiedAt": 1571120899000,
            "status": "booked",
            "start": 1767152700000,
            "clinicName": "Adult Echo Clinic",
            "reservationId": 523067,
            "latitude": 0.0,
            "longitude": 0.0,
            "reschAppYn": "Y",
            "cancelAppYn": "Y",
            "participant": {
                "id": "3.20068.523067",
                "actorId": "67.20068.14836",
                "status": "accepted",
                "type": "PART"
            },
            "reasons": [
                {
                    "reasonId": 12,
                    "reason": "Unable to get time"
                },
                {
                    "reasonId": 13,
                    "reason": "Inconvenient"
                }
                // Additional reasons are omitted for brevity.
            ],
            "estTypeCode": 106,
            "description": "Adult Echo Clinic | 31-Dec-2019 | 07:45",
            "estCode": 20068,
            "estName": "Directorate General of Information Technology",
            "estNameNls": "المديرية العامة لتقنية المعلومات"
        }
    ]
}
```
### Fields:

- version (string): API version.
- code (integer): Status code of the operation.
- message (string): Description regarding the result.
- result (array): An array of appointment details.
    - id (string): Identifier for the appointment.
    - profileCode (integer): Profile code associated with the appointment.
    - lastModifiedBy (integer): Last modified by establishment code.
    - lastModifiedAt (integer): Timestamp of the last modification.
    - status (string): Appointment status.
    - start (integer): Start timestamp of the appointment.
    - clinicName (string): Name of the clinic.
    - reservationId (integer): Reservation ID.
    - latitude (float): Latitude for the location.
    - longitude (float): Longitude for the location.
    - reschAppYn (string): Indicates if rescheduling is allowed ('Y' for yes).
    - cancelAppYn (string): Indicates if cancellation is allowed ('Y' for yes).
    - participant (object): Details about the participant in the appointment.
    - reasons (array): List of reasons related to appointment management.
    - estTypeCode (integer): Establishment type code.
    - description (string): Description of the appointment.
    - estCode (integer): Establishment code.
    - estName (string): Name of the establishment.
    - estNameNls (string): Localized name of the establishment.

### Error/Other Responses

1. #### Invalid Token
- HTTP Status Code: 401 (Unauthorized)
##### Content-Type: application/json
##### Body:
```
{
    "error": "invalid_token",
    "error_description": "d0816a77-af67-43fc-bad1-2edb2aae3dc51"
}
```

2. #### No-record found
- HTTP Status Code: 200 (OK)
#### Content-Type: application/json
#### Body:
```
{
    "version": "v2",
    "code": 4,
    "message": "No Record Found",
    "result": []
}
```
> This document provides a comprehensive guide for developers to understand and integrate with the

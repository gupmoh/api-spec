# Medical Report Request Submission
- 	Action: The GUP system submits the report request to MOH for approval.
- 	Process: GUP posts the request to a Kafka topic for processing.


 ```
 "payload": {
    "civilId": "123456",
    "patientId": "56465",
    "estCode": "20068",
    "deptCode": "556",
    "reasonId": "101",
    "remarks": "Patient requires a detailed medical report.",
    "mobileNo": "9876543210",
    "reportTypeId": "1",
    "selfOrDependant":"S"
  }

```

## Payload Field Descriptions:
- civilId (string): Civil ID of the patient
- patientId (string): Patient ID .
- estCode (string): Establishment code / Health Insitute Code.
- deptCode (string): Clinical Department code
- reasonId (string): Reason ID for the report request 
- remarks (string): Additional remarks about the request , upto 150 characters (optional)
- mobileNo (string): Mobile phone number of the patient.  upto 20 characters (optional)
- reportTypeId (string): Report type ID
- selfOrDependant (string): this report for self or dependant

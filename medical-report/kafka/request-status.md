## MOH send the status (Approved / Rejected) to GUP-Kafka based on health Institue approval/rejection
- Action: moh will read the Review status from local institute and POST the status (approved/rejected) to Kafka

```
{
  "applicationStatusMessage": {
    "applicantCivilId": "62163078",
    "beneficiaryCivilId": null,
    "beneficiaryCrNumber": null,
    "ministryCode": "MOH",
    "serviceCode": "MOH_XXX",
    "applicationReferenceObject": "REF3",
    "applicationNumber": "AB1j232k",
    "applicationRedirectLink": null,
    "applicationStatusCode": "APPROVED",
    "applicationStatusTimestamp": "2024-09-17T14:17:04.529895600",
    "applicationStatusMessage": "Medical Report Request is approved"
  }
}

```
### Field Descriptions:
- applicantCivilId (string): Civil ID of the applicant.
- beneficiaryCivilId (string): Civil ID of the beneficiary (if applicable).
- beneficiaryCrNumber (string): Commercial registration number of the beneficiary (if applicable).
- ministryCode (string): Code representing the ministry
- serviceCode (string): Code representing the specific service requested
- applicationReferenceObject (string): Reference object associated with the application
- applicationNumber (string): Unique application number
- applicationRedirectLink (string): A link for redirecting the application 
- applicationStatusCode (string): Status code of the application
- applicationStatusTimestamp (string): Timestamp of the status update, in ISO format.
- applicationStatusMessage (string): Message explaining the status.

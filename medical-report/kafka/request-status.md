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

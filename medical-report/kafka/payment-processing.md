## Payment Processing
- Action: GUP collects payment from the user after approval.
- Process: GUP posts the payment status to Kafka.

```
"payload": {
   "civilId": "123456",
   "patientId": "56465",
   "estCode": "20068",
   "status": "PAID",
   "paymentRefNo": "xxxxxxx"
 }

```

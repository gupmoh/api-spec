## Payment Processing
- Action: GUP collects payment from the user after approval.
- Process: GUP posts the payment status to Kafka.

```
"payload": {
   "status": "PAID",
   "paymentRefNo": "xxxxxxx",
   "bankTransationId": "xxxxxxx"
 }

```

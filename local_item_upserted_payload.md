# Local Item Upserted Webhook Payload

```json
{
 "event_id": "evt-b43595523116439ba91e2dd6275fa636",
 "timestamp": "2020-11-11T18:21:51.470Z",
 "organization": "nacelle-sandbox",
 "local_item": {
   "id": "lit-5566310bc307334697cb54362b8e46cc",
   "experience": {
     "id": "exp-1e97c9b5a2ee4ba3bddfc6f75d095fdd",
     "key": "china",
     "name": "China",
     "country": "CHN",
     "currency": "CNY",
     "language": "zh"
   },
   "item": {
     "id": "cit-69f231b48dbf4fc9b2563a3e44c45fbf",
     "number": "13211236302948"
   },
   "pricing": {
     "price": {
       "currency": "CNY",
       "amount": 435.76,
       "label": "CN¥435.76",
       "base": {
         "amount": 63.18,
         "currency": "USD",
         "label": "US$63.18"
       },
       "includes": {
         "key": "vat",
         "label": "Includes VAT"
       },
       "key": "localized_item_price"
     },
     "attributes": {
       "compare_at": {
         "currency": "CNY",
         "amount": 571,
         "label": "CN¥571.00",
         "base": {
           "amount": 82.79,
           "currency": "USD",
           "label": "US$82.79"
         }
       }
     }
   },
   "status": "included"
 },
 "discriminator": "local_item_upserted"
}
```

# Catalog Item Upserted Webhook Payload

The catalog_upsert_item webhook will POST the following payload to the set URL:

```json
{
 "event_id": "evt-b300e2b3f4b8431885f0be5bcb7e9792",
 "timestamp": "2020-11-11T17:55:13.054Z",
 "organization": ":organization_id",
 "item": {
   "id": "cit-69f231b48dbf4fc9b2563a3e44c45fbf",
   "number": "13211236302948",
   "locale": "en-US",
   "name": "Blue Silk Tuxedo - large",
   "price": {
     "amount": 100,
     "currency": "USD",
     "label": "US$100.00"
   },
   "categories": [
     "men",
     "tuxedo"
   ],
   "attributes": {
     "weight": "276.0",
     "display_variant_title": "large",
     "url": "https://shopify.flow.io/products/blue-silk-tuxedo?variant=13211236302948",
     "option1": "large",
     "weight_unit": "g",
     "product_handle": "blue-silk-tuxedo",
     "product_type": "tuxedo",
     "taxable": "true",
     "product_id": "1436577398884",
     "compare_at": "76",
     "vendor": "Liam Fashions",
     "inventory_policy": "continue",
     "sku": "bst-lrg",
     "source": "shopify",
     "barcode": "123123434554",
     "inventory_management": "shopify",
     "product_title": "Blue Silk Tuxedo",
     "requires_shipping": "true",
     "shopify_discount_percent": "23.68421052631578947368421052631579",
     "fulfillment_service": "manual",
     "variant_title": "large",
     "grams": "276.0",
     "fulfillment_method": "physical"
   },
   "dimensions": {
     "product": {
       "weight": {
         "value": "276.0",
         "units": "gram"
       }
     }
   },
   "images": [
     {
       "url": "https://cdn.shopify.com/s/files/1/0030/9585/5204/products/man-adjusts-blue-tuxedo-bowtie_925x_e28a7439-b436-486d-b2f3-40ad6f5bef15.jpg?v=1582295729",
       "tags": [],
       "attributes": {
         "position": "1",
         "alt": "blue-tuxedo-test"
       }
     },
     {
       "url": "https://cdn.shopify.com/s/files/1/0030/9585/5204/products/man-adjusts-blue-tuxedo-bowtie_925x_e28a7439-b436-486d-b2f3-40ad6f5bef15_100x100.jpg?v=1582295729",
       "tags": [
         "thumbnail",
         "checkout"
       ],
       "attributes": {
         "position": "1",
         "alt": "blue-tuxedo-test"
       }
     }
   ],
   "description": "<h4>Buy two pairs of <a href=\"https://shopify.flow.io/products/led-high-tops\">LED High Tops</a> and get a FREE Blue Silk Tuxedo!</h4>\n <span style=\"font-size: 12px;\"> *Must add Blue Silk Tuxedo to your cart to receive the discount</span> \n<p> </p>"
 },
 "discriminator": "catalog_item_upserted_v2"
}
```

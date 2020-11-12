# Configuring Webhooks

The Flow Console provides an interface to set up webhooks and subscribe to specific events. Select "Organization Settings" / "Integrations" and scroll down to the `Webhooks` section [https://console.flow.io/nacelle-sandbox/organization/integrations].

Webhooks can be configured to be sent to a URL of your choosing, it just needs to be set up to receive POST requests.

I have gone ahead and configured two webhooks, one for catalog_item_upsert and one for local_item_upsert. You can trigger these webhooks through a PUT request to the https://api.flow.io/nacelle-sandbox/catalog/items/:item_number endpoint and update the catalog data.

Example:

The following cURL command will change the price, triggering both events as the item will be updated, and we will thus reprice the item in each experience..

In addition to the cURL, here is the same request in a POSTMAN collection that can be used to trigger the webhooks: https://www.getpostman.com/collections/1c096ff5b161a1ec401e

For the authorization, an API token can be generated directly in Flow Console within the `nacelle-sandbox` organization that can be used to make these requests. 

Obtaining your API key
API keys at Flow Commerce are associated with your user account and give you access to all organizations that you're a part of.
To create your API key, please visit Your Account in Console and then do the following:
Select your Organization
Select Organization Settings from the menu on the left and then select API Keys.
Once your API key is generated, you can validate it via cURL as shown below:

```bash
curl -d token=<your api key> https://api.flow.io/token-validations
```

All authentication to the Flow Commerce API is via HTTP Basic Authorization. Your API Key is your username, and there is no password.

# Secure Your Webhooks

Flow signs webhook payloads with an SHA-256 hash of the request body. This signature is available as a request header, X-Flow-Signature, whose value is the hex-encoded SHA-256 hash of the request body using a secret specified by you.

To create a secret, update your webhook settings for your organization with the following endpoint: https://api.flow.io/nacelle-sandbox/webhook/settings

The following example shows you how to secure your webhook using a secret:

API Request:
```
cURL
curl -X PUT -d @body.json -u <api-token>: https://api.flow.io/:organization/webhook/settings
```

body.json:
```json
{
 "secret": "secret",
 "retry_max_attempts": 6,
 "retry_sleep_ms": 60000,
 "sleep_ms": 0
}
```

API Response:
```json
{
 "retry_sleep_ms": 60000,
 "retry_max_attempts": 6,
 "sleep_ms": 0,
 "secret": "secret"
}
```

Once your webhook is secure, it is best practice to employ a secret verification mechanism.

The following snippet is an example (in Ruby) on a suggested verification approach:

```Ruby
#!/usr/bin/env ruby
require 'openssl'
SHARED_SECRET = 'secret'
PAYLOAD = '{}'
EXPECTED_CHECKSUM = 'sha-256=77325902caca812dc259733aacd046b73817372c777b8d95b402647474516e13'
def verify_signature(payload)
 digest = OpenSSL::Digest.new('sha256')
 signature = 'sha-256=' + OpenSSL::HMAC.hexdigest(digest, SHARED_SECRET, payload)
 raise "Checksum did not match!" unless signature == EXPECTED_CHECKSUM
end
```



Resend Webhook
--------------

When testing your webhook it may be useful to have SerpWow re-send the webhook POST. This is useful for debugging webhook connectivity without needing to re-run the Batch.

You can also re-send webhooks via the Dashboard on the Batch Result Set page.

### Example

GET`/batches/BATCH_ID/results/RESULT_SET_ID/resendwebhook`In the example below we resend the webhook POST for Result Set with ID `1` for Batch with `id=123456`:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/results/1/resendwebhook?api_key=demo
```

```
curl -L --get https://api.serpwow.com/live/batches/123456/results/1/resendwebhook
```

```
const axios = require('axios');

// make the http GET request to resend the webhook
axios.get('https://api.serpwow.com/live/batches/123456/results/1/resendwebhook')
  .then(response => {

    // print the JSON response
    console.log(JSON.stringify(response.data, 0, 2));

  }).catch(error => {
    // catch and print the error
    console.log(error);
  })
```

```
import requests

# make the http GET request resend the webhook
api_result = requests.get('https://api.serpwow.com/live/batches/123456/results/1/resendwebhook')

# print the JSON response
print(json.dumps(api_result.json()))
```

```
<?php

# make the http GET request to resend the webhook
$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/results/1/resendwebhook'));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$api_result = curl_exec($ch);
curl_close($ch);

# print the JSON response
echo $api_result;

?>
```
  
:::::

CopySerpWow responds with the following JSON if the request to resend the webhook was successful. If the request was unsuccessful (for example, if the Result Set did not originally have a webhook POST set, or the webhook POST fails) then the API responds with an `HTTP 400` status code with the `request_info.message` property containing details of the error.


```
{
  "request_info": {
    "success": true,
    "message": "Webhook POST resent successfully."
  }
}
```
Copy
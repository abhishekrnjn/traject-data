Update Destination
------------------

Destinations can be updated by making an`HTTP PUT`to the`/destinations/DESTINATION_ID`endpoint (where`DESTINATION_ID`is the`id`of the Destination). The body can be either`x-www-form-urlencoded`parameters or a`JSON`object.

The [parameters](/docs/destinations-api/create#parameters) for updating a Destination are the same as those used when [creating](/docs/destinations-api/create) a Destination.

### Example

PUT`/destinations/DESTINATION_ID`In the example below we update a Destination with`id=ABCDEFG` to be disabled:





image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
$ curl -X PUT "https://api.serpwow.com/live/destinations/ABCDEFG?api_key=demo" \
  -d enabled="false"
```

```
const axios = require('axios');
const body = {
  enabled: false,
}

axios.put('https://api.serpwow.com/live/destinations/ABCDEFG?api_key=demo', body)
  .then(response => {
    const apiResponse = response.data;

    console.log('Destination Updated: ' + JSON.stringify(apiResponse, 0, 2));

  }).catch(error => {
    console.log(error);
  });
```

```
import requests
import json

body = {
  'enabled': False,
}

api_result = requests.put('https://api.serpwow.com/live/destinations/ABCDEFG?api_key=demo', json=body)

api_response = api_result.json()

print "Destination Updated: ", json.dumps(api_response)
```

```
<?php

$body = http_build_query([
  'enabled' => false,
]);

$ch = curl_init('https://api.serpwow.com/live/destinations/ABCDEFG?api_key=demo');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "PUT");
curl_setopt($ch, CURLOPT_POSTFIELDS, $body);

$json = curl_exec($ch);
curl_close($ch);

$api_result = json_decode($json, True);

print_r($api_result);

echo "Destination Updated", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with a JSON object containing details of the updated Destination.

  
:::hint



**Verifying your Destination**  
Whenever you enable a previous disabled Destination, or update an existing Destination's credentials, SerpWow will upload and then delete a small test file to the Destination to verify connectivity. If this connectivity test fails then the update operation itself fails.  
:::

Next Steps

* [Create Destination](/docs/destinations-api/create)
* [List Destinations](/docs/destinations-api/list)

Update Batch
------------

Batches can be updated by making an`HTTP PUT`to the`/batches/BATCH_ID`endpoint (where`BATCH_ID`is the`id`of the Batch). The body can be either`x-www-form-urlencoded`parameters or a`JSON`object.

The [parameters](/docs/batches-api/batches/create#parameters) for updating a Batch are the same as those used when [creating](/docs/batches-api/batches/create) a Batch.

### Example

PUT`/batches/BATCH_ID`In the example below we update a Batch with`id=123456`to run weekly, on Monday at 8am:





image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
$ curl -X PUT "https://api.serpwow.com/live/batches/123456?api_key=demo" \
  -d schedule_type="weekly" \
  -d schedule_days_of_week="1" \
  -d schedule_hours="8"
```

```
const axios = require('axios');
const body = {
  schedule_type: 'weekly',
  schedule_days_of_week: '1',
  schedule_hours: '8',
}

axios.put('https://api.serpwow.com/live/batches/123456?api_key=demo', body)
  .then(response => {
    const apiResponse = response.data;

    console.log('Batch Updated: ' + JSON.stringify(apiResponse, 0, 2));

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

body = {
  'schedule_type': 'weekly',
  'schedule_days_of_week': '1',
  'schedule_hours': '8',
}

api_result = requests.put('https://api.serpwow.com/live/batches/123456?api_key=demo', json=body)

api_response = api_result.json()

print "Batch Updated: ", json.dumps(api_response)
```

```
<?php

$body = http_build_query([
  'schedule_type' => 'weekly',
  'schedule_days_of_week' => '1',
  'schedule_hours' => '8',
]);

$ch = curl_init('https://api.serpwow.com/live/batches/123456?api_key=demo');
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

echo "Batch Updated", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with a JSON object containing details of the updated Batch.

  
:::hint



A Batch can only be updated when it is not running. To check whether a Batch is currently running use the [Get Batch](/docs/batches-api/batches/get) endpoint.  
:::

Next Steps

* [Start Batch](/docs/batches-api/batches/start)
* [Get Batch](/docs/batches-api/batches/get)

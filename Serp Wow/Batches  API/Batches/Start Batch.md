Start Batch
-----------

Batches can be started by making an`HTTP GET`request to the`/batches/BATCH_ID/start`endpoint (where`BATCH_ID`is the`id`of the Batch). You must have sufficient search credits available on your account for the number of searches in the Batch.

You would typically start Batches that are set to `schedule_type=manual`but you can start a Batch with any`schedule_type`, just as long as it isn't currently running.

### Example

GET`/batches/BATCH_ID/start`In the example below we start a Batch with`id=123456`:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/start?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/start?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/start', { params })
  .then(response => {
    const apiResponse = response.data;

    console.log('Batch started.');

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/batches/123456/start', params)

api_response = api_result.json()

print "Batch started."
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/start', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$json = curl_exec($ch);
curl_close($ch);

$api_result = json_decode($json, true);

print_r($api_result);

echo "Batch started.", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with a JSON object confirming that the Batch has been started, or detailing the error if it has not been possible to start the Batch (i.e. there are insufficient search credits available on your account).

Next Steps

* [Get Batches](/docs/batches-api/batches/get)
* [List Batches](/docs/batches-api/batches/list)

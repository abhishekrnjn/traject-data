Stop Batch
----------

Batches can be stopped when they are in the `queued` or `running` state by making an`HTTP GET`request to the`/batches/BATCH_ID/stop`endpoint (where`BATCH_ID`is the`id`of the Batch).

When stopping a Batch that is currently `queued` you will be refunded for the credits allocated for that Batch run. If the Batch has already started running (i.e. it is in the state `running`) then a credit refund will not be issued, but the Batch will still be stopped.

### Example

GET`/batches/BATCH_ID/stop`In the example below we stop a Batch with`id=123456`:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/stop?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/stop?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/stop', { params })
  .then(response => {
    const apiResponse = response.data;

    console.log('Batch stopped.');

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/batches/123456/stop', params)

api_response = api_result.json()

print "Batch stopped."
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/stop', $queryString));
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

echo "Batch stopped.", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with a JSON object confirming that the Batch has been stopped, or detailing the error if it has not been possible to stop the Batch (i.e. if the Batch is not curently `queued` or `running`).

Next Steps

* [Get Batches](/docs/batches-api/batches/get)
* [List Batches](/docs/batches-api/batches/list)
* [Stop All Batches](/docs/batches-api/batches/stop-all)

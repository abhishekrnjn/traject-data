Stop All Batches
----------------

Stop all Batches on your account that are currently in the `queued` or `running` state by making an`HTTP GET`request to the`/batches/stopall`endpoint. The Batches will be set back to the `idle` state.

For Batches that are currently `queued` you will be refunded for the credits allocated for that Batch run. If the Batch has already started running (i.e. it is in the state `running`) then a credit refund will not be issued, but the Batch will still be stopped.

### Example

GET`/batches/stopall`

HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/stopall?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/stopall?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/stopall', { params })
  .then(response => {
    const apiResponse = response.data;

    console.log('Batches stopped.');

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/batches/stopall', params)

api_response = api_result.json()

print "Batches stopped."
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/stopall', $queryString));
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

echo "Batches stopped.", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with a JSON object confirming that the Batches have been stopped.


```
{
  "request_info": {
    "success": true,
    "message": "23 Batches stopped"
  },
  "batches_stopped": 23,
  "batches_failed_to_stop": 0
}
```
CopyNext Steps

* [Get Batches](/docs/batches-api/batches/get)
* [List Batches](/docs/batches-api/batches/list)

Delete Batch
------------

Batches can be deleted by making an`HTTP DELETE`request to the`/batches/BATCH_ID`endpoint (where`BATCH_ID`is the`id`of the Batch you wish to delete).

  
:::hint



A Batch can only be deleted when it is not running. To check whether a Batch is currently running use the [Get Batch](/docs/batches-api/batches/get) endpoint.  
:::

### Example

DELETE`/batches/BATCH_ID`In the example below we delete a Batches with`id=123456`:





image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
$ curl -X DELETE "https://api.serpwow.com/live/batches/123456?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.delete('https://api.serpwow.com/live/batches/123456', { params })
  .then(response => {

    console.log('Batch deleted.');

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

api_result = requests.delete('https://api.serpwow.com/live/batches/123456?api_key=demo')

print ("Batch deleted.")
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "DELETE");

$json = curl_exec($ch);
curl_close($ch);

echo "Batch deleted.", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with a JSON object confirming that the Batch has been deleted, or detailing the error if it has not been possible to delete the Batch:


```
{
  "request_info": {
    "success": true,
    "message": "batch deleted"
  }
}
```
CopyNext Steps

* [Get Batches](/docs/batches-api/batches/get)
* [List Batches](/docs/batches-api/batches/list)

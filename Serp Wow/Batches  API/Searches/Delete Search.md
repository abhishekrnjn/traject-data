Delete Search
-------------

Searches can be deleted by making an `HTTP DELETE`request to the `/batches/BATCH_ID/SEARCH_ID`endpoint (where `SEARCH_ID`is the `id`of the Search to delete and `BATCH_ID`is the `id`of the Batch the Search belongs to).

  
:::hint



**Batch Status**  
Searches can only be deleted from a Batch when it is not running. To check whether a Batch is currently running use the [Get Batch](/docs/batches-api/batches/get) endpoint.  
:::

  
:::hint



**Deleting Multiple Searches**  
You should make calls to the Delete Search endpoint sequentially, rather than in parallel, as it is designed to remove Searches one by one. If you make too many concurrent calls you will receive an `HTTP 429` error. For mass-delete operations consider deleting and re-creating the Batch as this is typically quicker.  
  
Alternatively if your use-case requires mass deletion of Searches you may make an `HTTP DELETE` request to the `/batches/BATCH_ID/searches` endpoint with the `Content-Type` HTTP header set to `application/json` and the body of the request being an array of Search ID strings. The platform will then delete each of the IDs specified.  
:::

### Example

DELETE`/batches/BATCH_ID/SEARCH_ID`In the example below we delete a Search with `id=ABCDEFGHIJKLMNOP`from Batch with `id=123456`:





image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
$ curl -X DELETE "https://api.serpwow.com/live/batches/123456/ABCDEFGHIJKLMNOP?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.delete('https://api.serpwow.com/live/batches/123456/ABCDEFGHIJKLMNOP', { params })
  .then(response => {

    console.log('Search deleted.');

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

api_result = requests.delete('https://api.serpwow.com/live/batches/123456/ABCDEFGHIJKLMNOP?api_key=demo')

print ("Search deleted.")
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/ABCDEFGHIJKLMNOP', $queryString));
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

echo "Search deleted.", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with a JSON object confirming that the Search has been deleted, or detailing the error if it has not been possible to delete the Search:




Success JSON


No Search


No Batch  
:::::codeblocktabs


```
{
  "request_info": {
    "success": true,
    "message": "Search deleted"
  }
}
```

```
{
  "request_info": {
    "success": false,
    "message": "No Search with ID 'ABCDEFGHIJKLMNOP' was found in this Batch, please check the ID and try again"
  }
}
```

```
{
  "request_info": {
    "success": false,
    "message": "Batch with ID '123456' was not found"
  }
}
```
  
:::::

CopyNext Steps

* [Update Search](/docs/batches-api/searches/update)
* [List Search](/docs/batches-api/searches/list)

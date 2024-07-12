Update Search
-------------

Searches within a Batch can be updated by making an`HTTP PUT`to the`/batches/BATCH_ID/SEARCH_ID`endpoint (where`SEARCH_ID`is the`id`of the Search and`BATCH_ID`is the`id`of the Batch the Search belongs to). The body can be either`x-www-form-urlencoded`parameters or a`JSON`object.

The [parameters](/docs/search-api/searches/parameters) for updating a Search are the same as those used when making a call via the [Search API](/docs/search-api).

  
:::hint



**Batch Status**  
Searches can only be updated when the Batch they belong to is not running. To check whether a Batch is currently running use the [Get Batch](/docs/batches-api/batches/get) endpoint.  
:::

  
:::hint



**Updating Multiple Searches**  
You should make calls to the Update Search endpoint sequentially, rather than in parallel, as it is designed to update Searches one by one. If you make too many concurrent calls you will receive an `HTTP 429` error. For mass-update operations consider deleting and re-creating the Batch as this is typically quicker.  
:::

### Example

PUT`/batches/BATCH_ID/SEARCH_ID`In the example below we update a Search with`id=ABCDEFGHIJKLMNOP`within a Batch with`id=123456`.





image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
$ curl -X PUT "https://api.serpwow.com/live/batches/123456/ABCDEFGHIJKLMNOP?api_key=demo" \
  -d q="burger king"
```

```
const axios = require('axios');
const body = {
  "q": "burger king"
}

axios.put('https://api.serpwow.com/live/batches/123456/ABCDEFGHIJKLMNOP?api_key=demo', body)
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
  "q": "burger king"
}

api_result = requests.put('https://api.serpwow.com/live/batches/123456/ABCDEFGHIJKLMNOP?api_key=demo', json=body)

api_response = api_result.json()

print "Batch Updated: ", json.dumps(api_response)
```

```
$body = http_build_query([
  
  "q" => "burger king"

]);

$ch = curl_init('https://api.serpwow.com/live/batches/123456/ABCDEFGHIJKLMNOP?api_key=demo');
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

$api_result = json_decode($json, true);

echo "Batch Updated", PHP_EOL;
```
  
:::::

CopySerpWow responds with a JSON object containing details of the Search fields that have been updated:


```
{
  "request_info": {
    "success": true
  },
  "search": {
    "q": "burger king"
  }
}
```
CopyNext Steps

* [Delete Searches](/docs/batches-api/searches/delete)
* [List Searches](/docs/batches-api/searches/list)

Create Searches
---------------

Adding Searches to a Batch is achieved by making an `HTTP PUT`to the `/batches/BATCH_ID`endpoint (where `BATCH_ID`is the `id`of the Batch to add Searches to). The body of the request should be a `JSON`array of `search`objects (up to 1000 Searches can be added per call). The maximum number of Searches per Batch is 15,000 (or 100 when adding searches with `include_html=true` set).

The `/batches/BATCH_ID`endpoint used for adding Searches to a Batch is the same endpoint as used when [Updating a Batch](/docs/batches-api/batches/update), we've just listed them seperately in the Docs for ease of reference.

The [parameters](/docs/search-api/searches/parameters) for creating a Search are the same as those used when making a request via the [Search API](/docs/search-api).

  
:::hint



**Batch Status**  
Searches can only be added to a Batch when the Batch is not running. To check whether a Batch is currently running use the [Get Batch](/docs/batches-api/batches/get) endpoint.  
:::

  
:::hint



**Concurrency when Creating Searches**  
You should make calls to the Create Search endpoint sequentially, rather than in parallel. Each call can contain up to 1000 Search to add though. If you make too many concurrent calls you will receive an `HTTP 429` error.  
:::

  
:::hint



**Using `include_html=true` in Batches**  
When adding searches with `include_html=true` to a Batch the maximum number of searches per Batch is 100 (rather than 15,000) because including the HTML within the response makes the Batch Result Sets much larger. The limit is in place to ensure Result Set files are of a manageable size. If you have need to run a large number of searches all with `include_html=true` then simply split the searches across multiple 100-search Batches.  
:::

### Example

PUT`/batches/BATCH_ID`In the example below we add a new Search to a Batch with `id=123456`:

  
:::hint



Custom IDs  
When you add a Search to a Batch SerpWow assigns it an unique `id` - you can use this id to track the Search across multiple Result Sets.  
  
SerpWow also lets you specify your own `custom_id`, in addition to the SerpWow-assigned id, making it easy to use an ID from your app track Searches.  
:::





image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
$ curl -X PUT "https://api.serpwow.com/live/batches/123456?api_key=demo" \
  -H "Content-Type: application/json" \
  -d "{\"searches\": [{\"q\":\"mcdonalds\",\"location\":\"United States\",\"search_type\":\"images\",\"custom_id\":\"MyCustomID_001\"}]}"
```

```
const axios = require('axios');
const body = { searches: [
{
  "q": "mcdonalds",
  "location": "United States",
  "search_type": "images",
  "custom_id": "MyCustomID_001"
}]}

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
import json

body = { 
  "searches": [
  {
  "q": "mcdonalds",
  "location": "United States",
  "search_type": "images",
  "custom_id": "MyCustomID_001"
}]}

api_result = requests.put('https://api.serpwow.com/live/batches/123456?api_key=demo', json=body)

api_response = api_result.json()

print "Batch Updated: ", json.dumps(api_response)
```

```
<?php
      
$body = [ "searches" => array([
  "q" => "mcdonalds",
  "location" => "United States",
  "search_type" => "images",
  "custom_id" => "MyCustomID_001"
])];

$ch = curl_init('https://api.serpwow.com/live/batches/123456?api_key=demo');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "PUT");
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($body));

$json = curl_exec($ch);
curl_close($ch);

$api_result = json_decode($json, true);

print_r($api_result);

echo "Batch Updated", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with the following JSON confirming the Searches have been successfully created. Note the `searches_total_count`now reflects the count of the Searches the Batch has, including those just added. To List the Searches in the Batch use the [List Searches](/docs/batches-api/searches/list) endpoint:


```
{
  "request_info": {
    "success": true
  },
  "batch": {
    "id": "123456",
    "created_at": "2020-01-01T00:00:00.000Z",
    "name": "My First Batch",
    "schedule_type": "daily",
    "enabled": true,
    "status": "idle",
    "searches_total_count": 2,
    "searches_page_count": 1,
    "results_count": 0,
    "schedule_hours": [
      9,
      17
    ],
    "notification_email": "john.smith@example.com",
    "notification_as_json": false,
    "notification_as_jsonlines": false,
    "notification_as_csv": false
  }
}
```
CopyNext Steps

* [Update Search](/docs/batches-api/searches/update)
* [Delete Search](/docs/batches-api/searches/delete)
* [List Searches](/docs/batches-api/searches/list)

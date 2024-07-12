List Searches
-------------

You can List the Searches for a Batch by making making a`HTTP GET`request to the`/batches/BATCH_ID/searches/PAGE`endpoint (where`BATCH_ID`is the`id`of the Batch to get Searches for, and`PAGE`is the page of Searches to get).

The`/batches/BATCH_ID/searches/PAGE`endpoint returns the Searches for a Batch in pages of 1000 Searches per page. Pages start at`1`. You can find out how many pages a Batch has by inspecting the`searches_page_count`field returned from the [Get Batch](/docs/batches-api/batches/get) endpoint.

SerpWow also provides two more endpoints to allow you to retrieve a download link for all Searches in a Batch, in either`JSON`or`CSV`format.

### List Searches by Page

GET`/batches/BATCH_ID/searches/PAGE`In the example below we List`page 1`of the Searches for the Batch with`id=123456`:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/searches/1?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/searches/1?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/searches/1', { params })
  .then(response => {
    const apiResponse = response.data;

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/batches/123456/searches/1', params)

api_response = api_result.json()
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/searches/1', $queryString));
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

?>
```
  
:::::

CopySerpWow responds with the following JSON showing all the Searches on page 1 of the Batch:


```
{
  "request_info": {
    "success": true
  },
  "batch_id": "123456",
  "searches_page_current": 1,
  "searches_page_count": 1,
  "searches": [
    {
      "q": "mcdonalds",
      "location": "United States",
      "search_type": "images",
      "custom_id": "MyCustomID_001",
      "id": "ABCDEFGHIJKLMNOP"
    }
  ]
}
```
Copy### Get JSON Download Links

GET`/batches/BATCH_ID/searches/json`In the example below we retrieve download links for all Searches for Batch with`id=123456`in`JSON`format:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/searches/json?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/searches/json?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/searches/json', { params })
  .then(response => {
    const apiResponse = response.data;

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/batches/123456/searches/json', params)

api_response = api_result.json()
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/searches/json', $queryString));
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

?>
```
  
:::::

CopySerpWow responds with the following JSON detailing the total number of Searches `searches_total_count`, the total number of pages `searches_page_count` and a JSON file `download_link`for each page:


```
{
  "request_info": {
    "success": true
  },
  "batch_id": "123456",
  "searches_total_count": 1,
  "searches_page_count": 1,
  "download_links": {
    "pages": [
      "https://searches.serpwow.com/Batch_Searches_123456_Page_1.json"
    ]
  }
}
```
Copy### Get CSV Download Links

GET`/batches/BATCH_ID/searches/csv`In the example below we retrieve download links for all Searches for Batch with`id=123456`in`CSV`format:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/searches/csv?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/searches/csv?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/searches/csv', { params })
  .then(response => {
    const apiResponse = response.data;

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/batches/123456/searches/csv', params)

api_response = api_result.json()
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/searches/csv', $queryString));
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

?>
```
  
:::::

CopySerpWow responds with the following JSON detailing the total number of Searches `searches_total_count`, the total number of pages `searches_page_count` and a CSV file `download_link`for each page:


```
{
  "request_info": {
    "success": true
  },
  "batch_id": "123456",
  "searches_total_count": 1,
  "searches_page_count": 1,
  "download_links": {
    "pages": [
      "https://searches.serpwow.com/Batch_Searches_123456_Page_1.csv"
    ]
  }
}
```
CopyNext Steps

* [Listing Result Sets](/docs/batches-api/results/list)
* [Getting Result Sets](/docs/batches-api/results/get)

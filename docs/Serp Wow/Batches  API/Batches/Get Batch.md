Get Batch
---------

You can get a Batch by making making a`HTTP GET`request to the`/batches/BATCH_ID`endpoint (where`BATCH_ID`is the`id`of the Batch you wish to get).

SerpWow will return all information about the Batch, including whether it is currently running and how many Searches and Results Sets the Batch currently has.

  
:::hint



Note that the Batch Get endpoint just returns counts of the number of Searches and Result Sets the Batch contains. If you wish to retrieve the actual Searches or Result Sets in the Batch you should use the [List Searches](/docs/batches-api/searches/list) and [List Result Sets](/docs/batches-api/results/list) endpoints.  
:::

### Example

GET`/batches/BATCH_ID`In the example below we Get a Batch with`id=123456`:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456', { params })
  .then(response => {
    const apiResponse = response.data;

    console.log('Batch Name: ' + apiResponse.batch.name);

  }).catch(error => {
    console.log(error);
  });
```

```
import requests

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/batches/123456', params)

api_response = api_result.json()

print "Batch Name: ", api_response['batch']['name']
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

$json = curl_exec($ch);
curl_close($ch);

$api_result = json_decode($json, true);

print_r($api_result);

echo "Batch Name: ", $api_result['batch']['name'], PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with the following JSON showing all details of the Batch:


```
{
  "request_info": {
    "success": true
  },
  "batch": {
    "id": "123456",
    "created_at": "2020-01-01T00:00:00.000Z",
    "name": "My First Batch",
    "schedule_type": "manual/daily/weekly/monthly",
    "priority": "normal",
    "destination_ids": [
      "destination_id_1",
      "destination_id_2"
    ],
    "enabled": true,
    "status": "idle/queued/running",
    "search_total_count": 0,
    "search_page_count": 0,
    "credits_required": 0,
    "next_result_set_id": 1,
    "results_count": 0,
    "schedule_hours": [
      9,
      17
    ],
    "notification_email": "john.smith@example.com",
    "notification_as_json": false,
    "notification_as_jsonlines": false,
    "notification_as_csv": true
  }
}
```
CopyNext Steps

* [List Searches](/docs/batches-api/searches/list)
* [List Result Sets](/docs/batches-api/results/list)

List Result Sets
----------------

You can List all of the Result Sets for a Batch by making a `HTTP GET`request to the `/Batches/BATCH_ID/results`endpoint (where `BATCH_ID`is the `id`of the Batch to get Result Sets for). SerpWow retains Result Sets for 14 days so you should download your Result Set data within this 14 day window.

### Example

GET`/batches/BATCH_ID/results`In the example below we List all of the Result Sets for the Batch with `id=123456`:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/results?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/results?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/results', { params })
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

api_result = requests.get('https://api.serpwow.com/live/batches/123456/results', params)

api_response = api_result.json()
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/results', $queryString));
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

CopySerpWow responds with the following JSON showing all the Results Sets for the Batch. Note the `results`array contains a list of all of the Result Sets. The `id`property of a Result Set should be used with the [Get Result Set](/docs/batches-api/results/get) endpoint to retrieve the actual results within the Result Set.

**Note** the `results` array is sorted by the most recently run Result Set first.


```
{
  "request_info": {
    "success": true
  },
  "batch_id": "123456",
  "batch": {
    "id": "123456",
    "created_at": "2019-01-01T00:00:00.000Z",
    "name": "My First Batch",
    "schedule_type": "daily",
    "enabled": true,
    "status": "idle",
    "searches_total_count": 1,
    "searches_page_count": 1,
    "results_count": 1,
    "schedule_hours": [
      9,
      17
    ],
    "notification_email": "john.smith@example.com",
    "notification_as_json": false,
    "notification_as_jsonlines": false,
    "notification_as_csv": true
  },
  "results_count": 1,
  "results": [
    {
      "id": 1,
      "started_at": "2019-01-02T00:00:00.000Z",
      "ended_at": "2019-01-02T00:00:10.000Z",
      "expires_at": "2019-01-08T00:00:10.000Z",
      "results_page_count": 1,
      "searches_completed": 1,
      "searches_failed": 0,
      "searches_total": 1,
      "webhook_status": {
        "status": "ok",
        "log": [
          {
            "date_time": "2020-01-01T00:00:00.000Z",
            "text": "Webhook POST completed successfully."
          }
        ]
      },
      "destination_status": {
        "DESTINATION_ID": {
          "status": "ok",
          "log": [
            {
              "date_time": "2020-01-01T00:00:00.000Z",
              "text": "Destination upload completed successfully."
            }
          ]
        }
      }
    }
  ]
}
```
Copy
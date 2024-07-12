Get Result Set
--------------

You can retrieve the results within a Result Set by making making an`HTTP GET`request to the`/batches/BATCH_ID/results/RESULT_SET_ID`endpoint (where`BATCH_ID`is the`id`of the Batch to retrieve results for, and`RESULT_SET_ID`is the`id`of the Result Set within that Batch).

### Get Result Set as JSON

GET`/batches/BATCH_ID/results/RESULT_SET_ID`In the example below we retrieve a Result Set with`id=1`in Batch with`id=123456`in`JSON`format:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/results/1?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/results/1?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/results/1', { params })
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

api_result = requests.get('https://api.serpwow.com/live/batches/123456/results/1', params)

api_response = api_result.json()
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/results/1', $queryString));
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

CopySerpWow responds with the following JSON showing the Result Set details and `download_links`for each page of JSON files containing the results:


```
{
  "request_info": {
    "success": true
  },
  "batch_id": "123456",
  "result": {
    "id": 1,
    "started_at": "2019-01-02T00:00:00.000Z",
    "ended_at": "2019-01-02T00:00:10.000Z",
    "expires_at": "2019-01-08T00:00:10.000Z",
    "results_page_count": 1,
    "searches_completed": 1,
    "searches_failed": 0,
    "searches_total": 1,
    "download_links": {
      "pages": [
        "https://results.serpwow.com/Batch_Results_123456_1_Page_1.json"
      ],
      "all_pages": "https://results.serpwow.com/Batch_Results_123456_1_All_Pages.zip"
    },
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
}
```
Copy### Get Result Set as JSON Lines

GET`/batches/BATCH_ID/results/RESULT_SET_ID/jsonlines`In the example below we retrieve a Result Set with`id=1`in Batch with`id=123456`in`JSON Lines`format:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/results/1/jsonlines?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/results/1/jsonlines?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/results/1/jsonlines', { params })
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

api_result = requests.get('https://api.serpwow.com/live/batches/123456/results/1/jsonlines', params)

api_response = api_result.json()
```

```
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/results/1/jsonlines', $queryString));
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
```
  
:::::

CopySerpWow responds with the following JSON showing the Result Set details and `download_links` for each page of JSON Lines files containing the results:


```
{
  "request_info": {
    "success": true
  },
  "batch_id": "123456",
  "result": {
    "id": 1,
    "started_at": "2019-01-02T00:00:00.000Z",
    "ended_at": "2019-01-02T00:00:10.000Z",
    "expires_at": "2019-01-08T00:00:10.000Z",
    "results_page_count": 1,
    "searches_completed": 1,
    "searches_failed": 0,
    "searches_total": 1,
    "download_links": {
      "pages": [
        "https://results.serpwow.com/Batch_Results_123456_1_Page_1.jsonl"
      ],
      "all_pages": "https://results.serpwow.com/Batch_Results_123456_1_All_Pages_jsonlines.zip"
    },
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
}
```
Copy### Get Result Set as CSV

GET`/batches/BATCH_ID/results/RESULT_SET_ID/csv`We provide a further endpoint,`/batches/BATCH_ID/results/RESULT_SET_ID/csv`, to retrieve the Result Set in`CSV`format.

When using this endpoint you can supply a`csv_fields`querystring parameter to determine the fields that are included in the CSV file. the`csv_fields`parameter should be specified as a comma seperated list of fields (in nested field, dot notation, format). For more information see the [CSV Fields Reference](/docs/search-api/reference/csv-fields).

In the example below we retrieve a Result Set with`id=1`in Batch with`id=123456`in`CSV`format:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches/123456/results/1/csv?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches/123456/results/1/csv?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches/123456/results/1/csv', { params })
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

api_result = requests.get('https://api.serpwow.com/live/batches/123456/results/1/csv', params)

api_response = api_result.json()
```

```
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches/123456/results/1/csv', $queryString));
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
```
  
:::::

CopySerpWow responds with the following JSON showing the Result Set details and `download_links`for each page of CSV files containing the results:


```
{
  "request_info": {
    "success": true
  },
  "batch_id": "123456",
  "result": {
    "id": 1,
    "started_at": "2019-01-02T00:00:00.000Z",
    "ended_at": "2019-01-02T00:00:10.000Z",
    "expires_at": "2019-01-08T00:00:10.000Z",
    "results_page_count": 1,
    "searches_completed": 1,
    "searches_failed": 0,
    "searches_total": 1,
    "download_links": {
      "pages": [
        "https://results.serpwow.com/Batch_Results_123456_1_Page_1.csv"
      ],
      "all_pages": "https://results.serpwow.com/Batch_Results_123456_1_All_Pages_246f6e2e561c90958384aa76e455e2bc95ad3a01.csv"
    },
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
}
```
Copy
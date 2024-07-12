List Batches
------------

You can List all of the Batches currently set up on your account by making making a `HTTP GET`request to the `/batches`endpoint.

  
:::hint



Note that the Batch List endpoint is rate-limited to 60 requests per minute. For real-time updates as to your Batch status it is recommended you use Webhooks.  
:::

### Parameters

The following querystring (HTTP GET) parameters allow you to refine the results returned by the Batches List API.

| Parameter | Required | Description |
| --- | --- | --- |
| api\_key | required | The API key for your account. |
| only\_with\_results | optional | Set to only\_with\_results=true to only return Batches that have Result Sets available. |
| only\_without\_results | optional | Set to only\_without\_results=true to only return Batches that have no Result Sets available (i.e. that haven't yet been run). |
| search\_term | optional | Limits the returned Batches to just those containing the search\_term in their name. |
| search\_type | optional | Determines how the search\_term parameter is treated. Valid values are:Parameter ValuescontainsDefault returns Batches that contains all of the words (split by spaces) in the search\_term in their name or id properties (case-insensitive). Non alphanumeric characters are replaced by spaces.starts\_withReturns Batches whose name property starts with the search\_term (case-insensitive).ends\_withReturns Batches whose name property ends with the search\_term (case-insensitive).exactReturns Batches whose name property exactly matches the search\_term (case-sensitive). |
| status | optional | Filters the Batches returned to only those matching the given status. Valid values are all, idle, queued or running. Defaults to all. |
| created\_before | optional | Filters the Batches returned to only those with a created\_at date before the value specified. Should be specified as an ISO UTC timestamp, for example created\_before=2020-09-01T00:00:00.000Z. |
| created\_after | optional | Filters the Batches returned to only those with a created\_at date after the value specified. Should be specified as an ISO UTC timestamp, for example created\_after=2020-06-01T00:00:00.000Z. |
| last\_run\_before | optional | Filters the Batches returned to only those with a last\_run date before the value specified. Should be specified as an ISO UTC timestamp, for example last\_run\_before=2020-09-01T00:00:00.000Z. |
| last\_run\_after | optional | Filters the Batches returned to only those with a last\_run date after the value specified. Should be specified as an ISO UTC timestamp, for example last\_run\_after=2020-06-01T00:00:00.000Z. |
| destination\_id | optional | Filters the Batches returned to only those with the specified destination\_id set. You can view destination IDs on the Destinations page of the Dashboard or via the Destinations API. |
| page | optional | Set the page number of Batches to return, defaults to page=1. Unless otherwise specified using the page\_size parameter, 25 Batches are returned per page. |
| page\_size | optional | Sets the number of results returned per page. If the page\_size parameter is omitted then 25 results are returned per page by default. The maximum number of results returned per page is 1000 (page\_size=1000). |
| sort\_by | optional | The sort order to apply to the results. Valid values are created\_at (to sort by Batch creation date), last\_run (to sort by the date the Batch was last run), name (to sort by Batch name, the default), priority (to sort by Batch priority) or status (to sort by Batch status). Use in conjunction with the sort\_direction parameter. |
| sort\_direction | optional | The sort direction to return results. Valid values are descending or ascending (the default). Use in conjunction with the sort\_by parameter. |
### Example

GET`/batches`In the example below we List all the Batches on your account:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/batches?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/batches?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/batches?api_key=demo')
  .then(response => {
    const apiResponse = response.data;

    console.log("Total Batches: ", apiResponse.total_count);

    apiResponse.collections.map((batch, number) =>
      console.log((number + 1) + '. ' + batch.name);
      
  }).catch(error => {
    console.error(error);
  });
```

```
import requests

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/batches', { params })

api_response = api_result.json()

print "Total Batches: ", api_response['total_count']

for number, batch in enumerate(api_response['batches'], start=1):
    print "%s. %s" % (number, batch['name'])
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/batches', $queryString));
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

echo "Total Batches: ", $api_result['total_count'], PHP_EOL;

foreach ($api_result['batches'] as $number => $batch) {
  echo "{$number}. {$batch['name']}", PHP_EOL;
}

?>
```
  
:::::

CopySerpWow responds with the following JSON showing all the Batches on your SerpWow account:


```
{
  "request_info": {
    "success": true
  },
  "total_count": 2,
  "total_pages": 1,
  "current_page": 1,
  "count_this_page": 2,
  "batches": [
    {
      "id": "2A6F94BB",
      "created_at": "2020-01-01T00:00:01.000Z",
      "last_run": "2020-09-01T00:00:00.000Z",
      "name": "My Second Batch",
      "schedule_type": "weekly",
      "priority": "normal",
      "destination_ids": [
        "destination_id_1",
        "destination_id_2"
      ],
      "enabled": true,
      "status": "idle",
      "searches_total_count": 0,
      "searches_page_count": 0,
      "next_result_set_id": 1,
      "results_count": 0,
      "schedule_days_of_week": [
        0,
        3
      ],
      "schedule_hours": [
        8
      ],
      "notification_email": "john.smith@example.com",
      "notification_as_json": false,
      "notification_as_jsonlines": false,
      "notification_as_csv": false
    },
    {
      "id": "CAC8651D",
      "created_at": "2020-01-02T00:00:00.000Z",
      "last_run": "2020-09-01T00:10:00.000Z",
      "name": "My First Batch",
      "schedule_type": "daily",
      "priority": "normal",
      "destination_ids": [],
      "enabled": true,
      "status": "idle",
      "searches_total_count": 0,
      "searches_page_count": 0,
      "results_count": 0,
      "schedule_hours": [
        9,
        17
      ],
      "notification_email": "john.smith@example.com",
      "notification_as_json": false,
      "notification_as_csv": true
    }
  ]
}
```
CopyNext Steps

* [Webhook](/docs/batches-api/batches/webhook)
* [List Searches](/docs/batches-api/searches/list)
* [List Result Sets](/docs/batches-api/results/list)

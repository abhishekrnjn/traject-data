List Destinations
-----------------

You can List all of the Destinations currently set up on your account by making making a `HTTP GET`request to the `/destinations`endpoint.

### Parameters

The following querystring (HTTP GET) parameters allow you to refine the results returned by the Destinations List API.

| Parameter | Required | Description |
| --- | --- | --- |
| api\_key | required | The API key for your account. |
| search\_term | optional | Limits the returned Destinations to just those containing the search\_term in their name. |
| page | optional | Set the page number of Destinations to return, defaults to page=1. 10 Destinations are returned per page. |
| sort\_by | optional | The sort order to apply to the results. Valid values are type (to sort by Destination type) or name (to sort by Destination name). |
| sort\_direction | optional | The sort direction to return results. Valid values are descending or ascending (the default). Use in conjunction with the sort\_by parameter. |
### Example

GET`/destinations`In the example below we List page 1 of all the Destinations on your account:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/destinations?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/destinations?api_key=demo"
```

```
const axios = require('axios');

axios.get('https://api.serpwow.com/live/destinations?api_key=demo')
  .then(response => {
    const apiResponse = response.data;

    console.log("Total Destinations: ", apiResponse.usage.used);

    apiResponse.destinations.map((destination, number) =>
      console.log((number + 1) + '. ' + destination.name);
      
  }).catch(error => {
    console.error(error);
  });
```

```
import requests
import json

params = {
  'api_key': 'demo'
}

api_result = requests.get('https://api.serpwow.com/live/destinations', { params })

api_response = api_result.json()

for number, destination in enumerate(api_response['destinations'], start=1):
    print "%s. %s" % (number, destination['name'])
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/destinations', $queryString));
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

echo "Total Destinations: ", $api_result['usage']['used'], PHP_EOL;

foreach ($api_result['destinations'] as $number => $destination) {
  echo "{$number}. {$destination['name']}", PHP_EOL;
}

?>
```
  
:::::

CopySerpWow responds with the following JSON showing page 1 of all the Destinations on your SerpWow account:


```
{
  "request_info": {
    "success": true
  },
  "usage": {
    "used": 1,
    "limit": 50,
    "available": 49
  },
  "destinations": [
    {
      "id": "ABCDEFG",
      "name": "My First S3 Destination",
      "type": "s3",
      "enabled": true,
      "used_by": 0,
      "s3_bucket_name": "s3_bucket_name",
      "s3_path_prefix": "my_path_prefix"
    }
  ]
}
```
CopyNext Steps

* [Update Destination](/docs/destinations-api/update)
* [Delete Destination](/docs/destinations-api/delete)

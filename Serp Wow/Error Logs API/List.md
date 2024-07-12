List Error Logs
---------------

You can List all of the Error Logs currently set up on your account by making making a `HTTP GET`request to the `/errorlogs`endpoint.

  
:::hint



**Error Logs API Rate Limit**  
There is no charge for requests to the Error Logs API however the it is subject to a rate limit of 60 requests per minute. This limit includes requests made when accessing Error Logs via the [SerpWow dashboard](https://app.serpwow.com/errorlogs).  
  
In the event of the rate limit being hit an `HTTP 429` [response code](/docs/response-codes) will be returned.  
:::

### Parameters

The following querystring (HTTP GET) parameters allow you to refine the results returned by the Error Logs List API.

| Parameter | Required | Description |
| --- | --- | --- |
| api\_key | required | The API key for your account. |
| search\_term | optional | Limits the Error Logs returned to just those containing the search\_term in their parameters property. |
| page | optional | Set the page number of Error Logs to return, defaults to page=1. 10 Error Logs are returned per page. |
| sort\_by | optional | The sort order to apply to the results. Valid values are date (to sort by Error Log date) or count (to sort by Error Log count). |
| sort\_direction | optional | The sort direction to return results. Valid values are descending or ascending (the default). Use in conjunction with the sort\_by parameter. |
### Example

GET`/errorlogs`In the example below we List error logs on your account:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/errorlogs?api_key=demo
```

```
$ curl "https://api.serpwow.com/live/errorlogs?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.get('https://api.serpwow.com/live/errorlogs?api_key=demo')
  .then(response => {
    const apiResponse = response.data;

    console.log("Total Error Logs: ", apiResponse.results_count_total);

    apiResponse.logs.map((log, number) =>
      console.log((number + 1) + '. ' + log.id);
      
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

api_result = requests.get('https://api.serpwow.com/live/errorlogs', { params })

api_response = api_result.json()
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/errorlogs', $queryString));
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

echo "Total Error Logs: ", $api_result['results_count_total'], PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with the following JSON showing error logs from your account:

{"request\_info":{...}"logs":[...]"page":1"page\_count\_total":1"results\_count":1"results\_count\_total":1}Copy### 

SerpWow returns the following properties in the List Error Logs response:

| Property | Type | Description |
| request\_info | object | An object containing the status of your request.successbooleanTrue/false as to whether the request was successful. |
| logs | array | An array of Error Log objects. The Error Log object has the following properties:idstringThe unique ID of the Error Log.engine\_urlstringThe URL that SerpWow attempted to open on the host website to service this request. This can be useful to determine whether the host website is down or experiencing issues that would cause the SerpWow request to fail.api\_urlstringThe SerpWow API request that caused the errored response. Note that, for security, your API Key is removed from the URL.datestringAn ISO date/time stamp of the date of the most recent time this error was seen.countstringA count of the total number of times this error was seen.parametersstringA link to the website of the place result.thumbnailobjectAn object containing each of the API request parameters used in the request that generated the error.resultobjectAn object containing the JSON response the API gave in response to the errored request. |
| page | number | The current page of results. |
| page\_count\_total | number | The total number of pages of results that are available. |
| results\_count | number | The number of error log results on this page of results. |
| results\_count\_total | number | The total number of error logs on all pages. |
Next Steps

* [Account API](/docs/account-api)

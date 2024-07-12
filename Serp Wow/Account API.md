Account API
-----------

GET`/account`The SerpWow Account API allows you to check the number of searches made in the current month. There is no charge for calls made to the Account API.

The Account API also shows current platform status.



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/account?api_key=demo
```

```
$ curl --get https://api.serpwow.com/live/account \
  -d api_key="demo"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo"
}

// make the http GET request to SerpWow
axios.get('https://api.serpwow.com/live/account', { params })
  .then(response => {

    // print the JSON response from SerpWow
    console.log(JSON.stringify(response.data, 0, 2));

  }).catch(error => {
    // catch and print the error
    console.log(error);
  })
```

```
import requests
import json

# set up the request parameters
params = {
  'api_key': 'demo'
}

# make the http GET request to SerpWow
api_result = requests.get('https://api.serpwow.com/live/account', params)

# print the JSON response from SerpWow
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo'
]);

# make the http GET request to SerpWow
$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/account', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$api_result = curl_exec($ch);
curl_close($ch);

# print the JSON response from SerpWow
echo $api_result;
```
  
:::::

Copy### Parameters

The Account API takes a single parameter, the`api_key`to retrieve account information from.

| Parameter | Required | Description |
| --- | --- | --- |
| api\_key | required | The API key for your account. |
### Response

The Account API returns structured JSON showing your account details and platform status. The `usage_history` property contains detailed credit usage history for the past 3 months:

{"request\_info":{...}"account\_info":{...}}Copy
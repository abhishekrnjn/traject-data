Google Place Details Parameters
-------------------------------

GET`/search?engine=google&search_type=place_details`The Google Place Details Parameters are applicable when making a request with `search_type=place_details` to retrieve place details for a Place. The Place is specified in the `data_id` parameter, `data_id` values are returned from `search_type=places` [Places requests](/docs/search-api/searches/google/places).

If the `data_id` is not available you may also request a `place_details` request using a `data_cid` (a standardised Google Place identifier you may already have access to). However, `data_id` is the recommended identifier to use.

![]()Google Place Detail ResultsFor example, to request place detail results for a Place with `data_id=0x87b7122bd8e99a89:0xf20c18461109b2c0`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=place_details&data_id=0x87b7122bd8e99a89:0xf20c18461109b2c0
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d search_type="place_details" \
-d data_id="0x87b7122bd8e99a89:0xf20c18461109b2c0"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  search_type: "place_details",
  data_id: "0x87b7122bd8e99a89:0xf20c18461109b2c0"
}

// make the http GET request
axios.get('https://api.serpwow.com/live"/search', { params })
  .then(response => {

    // print the JSON response
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
  'api_key': 'demo',
  'search_type': 'place_details',
  'data_id': '0x87b7122bd8e99a89:0xf20c18461109b2c0'
}

# make the http GET request
api_result = requests.get('https://api.serpwow.com/live/search', params)

# print the JSON response
print(json.dumps(api_result.json()))
```

```
<?php
      
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'search_type' => 'place_details',
  'data_id' => '0x87b7122bd8e99a89:0xf20c18461109b2c0'
]);

# make the http GET request
$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/search', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$api_result = curl_exec($ch);
curl_close($ch);

# print the JSON response
echo $api_result;

?>
```
  
:::::

Copy### Google Place Details Parameters

The following parameters are available for all requests made when `search_type=place_details`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=place\_details. |
| data\_id | required | The data\_id of the Place to retrieve place details for. data\_id values are returned in Places requests.Note that either a data\_id or data\_cid identifier must be supplied. |
| data\_cid | required | The data\_cid (a standard Google Place identifier) of the Place to retrieve place details for. data\_cid values are returned in Places requests.Note that either a data\_id or data\_cid identifier must be supplied. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
Next Steps

* [Google Place Details Results](/docs/search-api/results/google/place-details)

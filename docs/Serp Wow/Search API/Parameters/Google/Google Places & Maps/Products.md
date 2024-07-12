Google Place Products Parameters
--------------------------------

GET`/search?engine=google&search_type=place_products`The Google Place Products Parameters are applicable when making a request with `search_type=place_products` to retrieve place products for a Place. The Place is specified in the `data_cid` parameter, `data_cid` values are returned from `search_type=places` [Places requests](/docs/search-api/searches/google/places).

  
:::hint



**`data_cid` IDs used in `place_products` requests**  
Note that `place_products` requests differ from `place_reviews` ([docs](/docs/search-api/searches/google/place-reviews)) and `place_photos` ([docs](/docs/search-api/searches/google/place-photos)) requests in that it required a `data_cid` instead of a `data_id` request parameter.  
  
Both `data_cid` and `data_id` IDs are returned in [Places requests](/docs/search-api/searches/google/places) requests.  
:::

![]()Google Place Product ResultsFor example, to request place product results for a Place with `data_cid=17441342146111713984`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=place_products&data_cid=17441342146111713984
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d search_type="place_products" \
-d data_cid="17441342146111713984"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  search_type: "place_products",
  data_cid: "17441342146111713984"
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
  'search_type': 'place_products',
  'data_cid': '17441342146111713984'
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
  'search_type' => 'place_products',
  'data_cid' => '17441342146111713984'
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

Copy### Google Place Products Parameters

The following parameters are available for all requests made when `search_type=place_products`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=place\_products. |
| data\_cid | required | The data\_cid of the Place to retrieve place products for. data\_cid values are returned in Places requests. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
Next Steps

* [Google Place Products Results](/docs/search-api/results/google/place-products)

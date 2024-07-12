Google Place Photos Parameters
------------------------------

GET`/search?engine=google&search_type=place_photos`The Google Place Photos Parameters are applicable when making a request with `search_type=place_photos` to retrieve place photos for a Place. The Place is specified in the `data_id` parameter, `data_id` values are returned from `search_type=places` [Places requests](/docs/search-api/searches/google/places).

  
:::hint



**Place Photo Category IDs**  
If shown, a `search_type=place_photos` will return a `categories` array containing photo categories. You can pass a place photos category ID in to the optional `category_id` parameter to refine your place photos request to just photos belonging to that category.  
:::

  
:::hint



**Place Photos Pagination**  
Place Photo results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead, each `search_type=place_photos` result will return a `next_page_token` in its' `pagination` object. This `next_page_token` can be passed in to the `next_page_token` request parameter to retrieve the next page of place photo results.  
:::

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_place_photos.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Place Photo ResultsFor example, to request place photo results for the data\_id `0x89c259cea3b62d4d:0x4519bf551f37923f`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=place_photos&data_id=0x89c259cea3b62d4d:0x4519bf551f37923f
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d search_type="place_photos" \
-d data_id="0x89c259cea3b62d4d:0x4519bf551f37923f"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  search_type: "place_photos",
  data_id: "0x89c259cea3b62d4d:0x4519bf551f37923f"
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
  'search_type': 'place_photos',
  'data_id': '0x89c259cea3b62d4d:0x4519bf551f37923f'
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
  'search_type' => 'place_photos',
  'data_id' => '0x89c259cea3b62d4d:0x4519bf551f37923f'
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

Copy### Google Place Photos Parameters

The following parameters are available for all requests made when `search_type=place_photos`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=place\_photos. |
| data\_id | required | The data\_id of the Place to retrieve place photos for. data\_id values are returned in Places requests. |
| category\_id | optional | An optional category ID to limit the returned photos to just those belonging to the given category. category\_id values, if shown for the given data\_id, are returned in the categories array in all search\_type=place\_photos results. |
| next\_page\_token | optional | Place Photo results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead, each search\_type=place\_photos result will return a next\_page\_token in its' pagination object. This next\_page\_token can be passed in to the next\_page\_token request parameter to retrieve the next page of place photo results. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
Next Steps

* [Google Place Photos Results](/docs/search-api/results/google/place-photos)

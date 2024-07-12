Google Place Reviews Parameters
-------------------------------

GET`/search?search_type=place_reviews`The Google Place Reviews Parameters are applicable when making a request with `search_type=place_reviews` to retrieve place reviews for a Place. The Place is specified in the `data_id` parameter, `data_id` values are returned from `search_type=places` [Places requests](/docs/search-api/searches/google/places).



**Place Review Topic IDs**  
If shown, a `search_type=place_reviews` will return a `topics` array containing review topics. You can pass a place reviews topic ID in to the optional `topic_id` parameter to refine your place reviews request to just reviews related to that topic.

**Place Reviews Pagination**  
Place Review results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead, each `search_type=place_reviews` result will return a `next_page_token` in its' `pagination` object. This `next_page_token` can be passed in to the `next_page_token` request parameter to retrieve the next page of place reviews results.![](https://apiimages.imgix.net/scaleserp/images/png/docs/google_place_reviews.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Place Review ResultsFor example, to request place review results for a Place with `data_id=0x89c259cea3b62d4d:0x4519bf551f37923f`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&search_type=place_reviews&data_id=0x89c259cea3b62d4d:0x4519bf551f37923f
```

```
curl -L --get https://api.scaleserp.com/search \
-d api_key="demo" \
-d search_type="place_reviews" \
-d data_id="0x89c259cea3b62d4d:0x4519bf551f37923f"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  search_type: "place_reviews",
  data_id: "0x89c259cea3b62d4d:0x4519bf551f37923f"
}

// make the http GET request
axios.get('https://api.scaleserp.com"/search', { params })
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
  'search_type': 'place_reviews',
  'data_id': '0x89c259cea3b62d4d:0x4519bf551f37923f'
}

# make the http GET request
api_result = requests.get('https://api.scaleserp.com/search', params)

# print the JSON response
print(json.dumps(api_result.json()))
```

```
<?php
      
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'search_type' => 'place_reviews',
  'data_id' => '0x89c259cea3b62d4d:0x4519bf551f37923f'
]);

# make the http GET request
$ch = curl_init(sprintf('%s?%s', 'https://api.scaleserp.com/search', $queryString));
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
Copy### Google Place Reviews Parameters

The following parameters are available for all requests made when `search_type=place_reviews`.

ParameterRequiredDescriptionsearch\_typerequiredShould be set to `search_type=place_reviews`.data\_idrequiredThe `data_id` of the Place to retrieve place reviews for. `data_id` values are returned in [Places requests](/docs/search-api/searches/google/places).topic\_idoptionalAn optional topic ID to limit the returned reviews to just those related to the given topic. `topic_id` values, if shown for the given `data_id`, are returned in the `topics` array in all `search_type=place_reviews` results.sort\_byoptionalDetermines how place reviews are sorted, valid values are `relevance`, `date`, `highest_rating` and `lowest_rating`. Defaults to `relevance`.next\_page\_tokenoptionalPlace Review results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead, each `search_type=place_reviews` result will return a `next_page_token` in its' `pagination` object. This `next_page_token` can be passed in to the `next_page_token` request parameter to retrieve the next page of place reviews results.hloptionalThe `hl` parameter determines the Google UI language to return results. View the full list of supported `hl`values [here](/docs/search-api/reference/google-languages). Defaults to `en`.Next Steps

* [Google Place Reviews Results](/docs/search-api/results/google/place-reviews)

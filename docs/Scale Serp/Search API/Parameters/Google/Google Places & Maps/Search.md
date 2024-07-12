Google Places Parameters
------------------------

GET`/search?search_type=places`Scale SERP parses Google Local & Maps results (i.e. local business listings) when the `search_type` parameter is set to `search_type=places`. When this parameter is set Scale SERP provides a `places_results` array in the result JSON that contains the [Places or Maps results](/docs/search-api/results/google/places).



**Google Local vs. Google Maps**  
`search_type=places` requests can be executed in two modes to retrieve data from a [Google Local results page](https://www.google.com/search?q=pizza&gl=us&hl=en&uule=w+CAIQICIgTWFuaGF0dGFuLE5ldyBZb3JrLFVuaXRlZCBTdGF0ZXM&tbm=lcl) or from a [Google Maps results page](https://www.google.com/maps/search/pizza/@43.437677,-3.8392765,15z).  
  
You set the Location of the `search_type=places` request using the `location` request parameter and this can be expressed as either a text location name from the [Locations API](/docs/locations-api/overview) (which will result in a [Google Local result](https://www.google.com/search?q=pizza&gl=us&hl=en&uule=w+CAIQICIgTWFuaGF0dGFuLE5ldyBZb3JrLFVuaXRlZCBTdGF0ZXM&tbm=lcl)), or as a latitude, longitude and zoom level (which will result in a [Google Maps result](https://www.google.com/maps/search/pizza/@43.437677,-3.8392765,15z)).### Google Local Parameters

If the `location` parameter is set to a location name from the [Locations API](/docs/locations-api/overview) (or any other free-form location name text) - for example `Manhattan,New+York,United+States` then results will be returned from a [Google Local](https://www.google.com/search?q=pizza&gl=us&hl=en&uule=w+CAIQICIgTWFuaGF0dGFuLE5ldyBZb3JrLFVuaXRlZCBTdGF0ZXM&tbm=lcl) page.



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&search_type=places&q=pizza&location=United+States
```

```
curl -L --get https://api.scaleserp.com/search \
-d api_key="demo" \
-d q="pizza" \
-d search_type="places" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  search_type: "places",
  location: "United+States"
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
  'q': 'pizza',
  'search_type': 'places',
  'location': 'United+States'
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
  'q' => 'pizza',
  'search_type' => 'places',
  'location' => 'United+States'
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
CopyResults are returned from a [Google Local](https://www.google.com/search?q=pizza&gl=us&hl=en&uule=w+CAIQICIgTWFuaGF0dGFuLE5ldyBZb3JrLFVuaXRlZCBTdGF0ZXM&tbm=lcl) page as shown below.

![]()Google Local PageThe following parameters are available for Google Local requests - i.e. requests made when `search_type=places` and the `location` value is provided as a `full_name` location name from the [Locations API](/docs/locations-api/overview) (or any other free-form location name text).

ParameterRequiredDescriptionqrequiredThe keyword you want to use to perform the Local search.locationoptionalDetermines the geographic location in which the query is executed. You can enter any location as free-text, but if you `full_name` value from the Scale SERP [built-in locations](/docs/locations-api) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the `location_auto`parameter).location\_autooptionalIf the `location`field is set to a Scale SERP [built-in location](/docs/locations-api) from the [Locations API](/docs/locations-api), and `location_auto`is set to `true` (default) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location. Valid values are `true` (default) to enable this behaviour or `false`to disable.uuleoptionalThe Google UULE parameter - use to pass through a custom `uule` parameter to Google. Scale SERP automatically generates the `uule` when you use the `location` parameter but we allow you to overwrite it directly by specifying a `uule` directly.google\_domainoptionalThe Google domain to use to run the search query. View the full list of supported `google_domain`values [here](/docs/search-api/reference/google-domains). Defaults to `google.com`.gloptionalThe `gl` parameter determines the Google country to use for the query. View the full list of supported `gl`values [here](/docs/search-api/reference/google-countries). Defaults to `us`.hloptionalThe `hl` parameter determines the Google UI language to return results. View the full list of supported `hl`values [here](/docs/search-api/reference/google-languages). Defaults to `en`.nfproptionalDetermines whether to exclude results from auto-corrected queries that were spelt wrong. Can be set to `1`to exclude auto-corrected results, or `0` (default) to include them.pageoptionalDetermines the page of results to return, defaults to `1`. Use in combination with the `num` parameter to implement pagination.max\_pageoptionalUse the `max_page` parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.  
  
See the [Pagination](/docs/search-api/pagination) docs for more information.numoptionalDetermines the number of results to show per page. Use in combination with the `page` parameter to implement pagination.  
  
**Note** the maximum number of results per page Google allow, for Places results, is `20`.### Google Maps Parameters

If the `location` parameter is set to a latitude, longitude and zoom value - for example `location=lat:43.437677,lon:-3.8392765,zoom:15` then results will be returned from a [Google Maps](https://www.google.com/maps/search/pizza/@43.437677,-3.8392765,15z) page.



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.serpwow.com/live/search?api_key=demo&search_type=places&q=pizza&location=location=lat:43.437677,lon:-3.8392765,zoom:15
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d q="pizza" \
-d search_type="places" \
-d location="location=lat:43.437677,lon:-3.8392765,zoom:15"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
api_key: "demo",
q: "pizza",
type: "places",
location: "location=lat:43.437677,lon:-3.8392765,zoom:15"
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
'q': 'pizza',
'search_type': 'places',
'location': 'location=lat:43.437677,lon:-3.8392765,zoom:15'
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
'q' => 'pizza',
'search_type' => 'places',
'location' => 'location=lat:43.437677,lon:-3.8392765,zoom:15'
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
Copy

**Formatting the `location` parameter for Google Maps requests**  
To get Google Maps results based on latitude and longitude coordinates you should specify your `location` parameter in the form `location=lat:43.437677,lon:-3.8392765,zoom:15` where `43.437677` is your latitude value, `-3.8392765` is your longitude value and `15` is your zoom value.  
  
Delimit each section with a comma `,`, and delimit each name/value pair with a colon `:`.  
  
Valid `zoom` values are between `3` (maximum zoom-out) and `21` (maximum zoom-in).  
  
Google can return results outside the bounds of the zoom level in some instances. If this behaviour is not desirable then specifying `strict:true` in the `location` parameter will only return results within the current zoom level. Eg. `lat:39.58467741051493,lon:-0.6752313712718961,zoom:15,strict:true`Results are returned from a [Google Maps](https://www.google.com/maps/search/pizza/@43.437677,-3.8392765,15z) page as shown below.

![]()Google Maps PageThe following parameters are available for Google Maps requests - i.e. requests made when `search_type=places` and the `location` value is provided as a longitude, latitude and zoom level.

ParameterRequiredDescriptionqrequiredThe keyword you want to use to perform the Google Maps search.locationoptionalDetermines the geographic location in which the query is executed.  
  
To get Google Maps results based on latitude and longitude coordinates you should specify your `location` parameter in the form `location=lat:43.437677,lon:-3.8392765,zoom:15` where `43.437677` is your latitude value, `-3.8392765` is your longitude value and `15` is your zoom value.  
  
Delimit each section with a comma `,`, and delimit each name/value pair with a colon `:`.  
  
Valid `zoom` values are between `3` (maximum zoom-out) and `21` (maximum zoom-in).  
  
**Note** include the `google_domain` and `hl` parameters to specify the Google domain and the UI language of the search results. By default, the Google domain and language are not based on the geographic coordinates (latitude/longitude) of the target country.google\_domainoptionalThe Google domain to use to run the search query. View the full list of supported `google_domain`values [here](/docs/search-api/reference/google-domains). Defaults to `google.com`.hloptionalThe `hl` parameter determines the Google UI language to return results. View the full list of supported `hl`values [here](/docs/search-api/reference/google-languages). Defaults to `en`.pageoptionalDetermines the page of results to return, defaults to `1`.  
  
**Note** that the number of results per page is fixed to `20` and that the `num` parameter has no effect when running Google Maps requests.max\_pageoptionalUse the `max_page` parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.  
  
See the [Pagination](/docs/search-api/pagination) docs for more information.Next Steps

* [Google Places Results](/docs/search-api/results/google/places)

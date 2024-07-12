Google Image Parameters
-----------------------

GET`/search?search_type=images`The Google Image Parameters are applicable when making a request with `search_type=images` to retrieve image results for a given search term. The search term is specified in the `q` parameter and the optional `location` parameter can be used to geo-locate the image request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

![]()Google Image ResultsFor example, to request image results for the keyword `pizza` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&search_type=images&q=pizza&location=United+States
```

```
curl -L --get https://api.scaleserp.com/search \
-d api_key="demo" \
-d q="pizza" \
-d search_type="images" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  search_type: "images",
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
  'search_type': 'images',
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
  'search_type' => 'images',
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
Copy### Google Image Parameters

The following parameters are available for all requests made when `search_type=images`.

ParameterRequiredDescriptionsearch\_typerequiredShould be set to `search_type=images`.qrequiredThe keyword you want to use to perform the Images search.locationoptionalDetermines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the Scale SERP [built-in locations](/docs/locations-api) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the `location_auto`parameter).location\_autooptionalIf the `location`field is set to a Scale SERP [built-in location](/docs/locations-api) from the [Locations API](/docs/locations-api), and `location_auto`is set to `true` (default) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location. Valid values are `true` (default) to enable this behaviour or `false`to disable.uuleoptionalThe Google UULE parameter - use to pass through a custom `uule` parameter to Google. Scale SERP automatically generates the `uule` when you use the `location` parameter but we allow you to overwrite it directly by specifying a `uule` directly.google\_domainoptionalThe Google domain to use to run the search query. View the full list of supported `google_domain`values [here](/docs/search-api/reference/google-domains). Defaults to `google.com`.gloptionalThe `gl` parameter determines the Google country to use for the query. View the full list of supported `gl`values [here](/docs/search-api/reference/google-countries). Defaults to `us`.hloptionalThe `hl` parameter determines the Google UI language to return results. View the full list of supported `hl`values [here](/docs/search-api/reference/google-languages). Defaults to `en`.lroptionalThe `lr` parameter limits the results to websites containing the specified language. View the full list of supported `lr`values [here](/docs/search-api/reference/google-lr-languages).croptionalThe `cr` parameter instructs Google to limit the results to websites in the specified country. View the full list of supported `cr`values [here](/docs/search-api/reference/google-cr-countries).images\_pageoptionalDetermines the page of results to get when `search_type=images`. For images Google will return 100 results per page (a Google-imposed limit). Use `images_page` to specify the page of results to retrieve, for example is `images_page=2` the API will return images 100-199.images\_coloroptionalAllows you to set the color of the images returned when `search_type=images`. Valid values are `any`, `black_and_white`, `transparent`, `red`, `orange`, `yellow`, `green`, `teal`, `blue`, `purple`, `pink`, `white`, `gray`, `black` or `brown`.images\_sizeoptionalAllows you to set the size of the images returned when `search_type=images`. Valid values are `large`, `medium`, or `icon`.images\_typeoptionalAllows you to set the size of the images returned when `search_type=images`. Allows you to set the type of the images returned when `search_type=images`. Valid values are `clipart`, `line_drawing`, or `gif`.images\_usageoptionalAllows you to specify the usage rights of the images returned when `search_type=images`. Valid values are `non_commercial_reuse_with_modification` or `non_commercial_reuse`.time\_periodoptionalDetermines the time period of the results shown. It can be set to `last_hour`, `last_day` (for the last 24 hours), `last_week` (for the last 7 days), `last_month`, `last_year`or `custom`. When using `custom`you must also specifiy one or both of the `time_period_min`or `time_period_max`parameters to define the custom time period.time\_period\_minoptionalDetermines the minimum (i.e. 'from') time to use when `time_period`is set to `custom`. Should be in the form `MM/DD/YYYY`, I.e. for 31st December 2018 `time_period_min`would be `12/31/2018`.time\_period\_maxoptionalDetermines the maximum (i.e. 'to') time to use when `time_period`is set to `custom`. Should be in the form `MM/DD/YYYY`, I.e. for 31st December 2018 `time_period_max`would be `12/31/2018`.safeoptionalDetermines whether `Safe Search`is enabled for the results. Can be set to `active`to enable Safe Search, or `off` to disable Safe Search.tbsoptionalSets a specific string to be added to the Google `tbs` parameter in the underlying Google query. The `tbs` parameter is normally generated automatically by the API, but it can be set explicitly also.Next Steps

* [Google Image Results](/docs/search-api/results/google/images)

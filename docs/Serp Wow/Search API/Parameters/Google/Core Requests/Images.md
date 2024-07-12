Google Image Parameters
-----------------------

GET`/search?engine=google&search_type=images`The Google Image Parameters are applicable when making a request with `search_type=images` to retrieve image results for a given search term. The search term is specified in the `q` parameter and the optional `location` parameter can be used to geo-locate the image request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_images.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Image ResultsFor example, to request image results for the keyword `pizza` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=images&q=pizza&location=United+States
```

```
curl -L --get https://api.serpwow.com/live/search \
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
  'q': 'pizza',
  'search_type': 'images',
  'location': 'United+States'
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
  'q' => 'pizza',
  'search_type' => 'images',
  'location' => 'United+States'
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

Copy### Google Image Parameters

The following parameters are available for all requests made when `search_type=images`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=images. |
| q | required | The keyword you want to use to perform the Images search. |
| location | optional | Determines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the SerpWow built-in locations then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the location\_autoparameter). |
| location\_auto | optional | If the locationfield is set to a SerpWow built-in location from the Locations API, and location\_autois set to true (default) then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location. Valid values are true (default) to enable this behaviour or falseto disable. |
| uule | optional | The Google UULE parameter - use to pass through a custom uule parameter to Google. SerpWow automatically generates the uule when you use the location parameter but we allow you to overwrite it directly by specifying a uule directly. |
| google\_domain | optional | The Google domain to use to run the search query. View the full list of supported google\_domainvalues here. Defaults to google.com. |
| gl | optional | The gl parameter determines the Google country to use for the query. View the full list of supported glvalues here. Defaults to us. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
| lr | optional | The lr parameter limits the results to websites containing the specified language. View the full list of supported lrvalues here. |
| cr | optional | The cr parameter instructs Google to limit the results to websites in the specified country. View the full list of supported crvalues here. |
| images\_page | optional | Determines the page of results to get when search\_type=images. For images Google will return 100 results per page (a Google-imposed limit). Use images\_page to specify the page of results to retrieve, for example is images\_page=2 the API will return images 100-199. |
| images\_color | optional | Allows you to set the color of the images returned when search\_type=images. Valid values are any, black\_and\_white, transparent, red, orange, yellow, green, teal, blue, purple, pink, white, gray, black or brown. |
| images\_size | optional | Allows you to set the size of the images returned when search\_type=images. Valid values are large, medium, or icon. |
| images\_type | optional | Allows you to set the size of the images returned when search\_type=images. Allows you to set the type of the images returned when search\_type=images. Valid values are clipart, line\_drawing, or gif. |
| images\_usage | optional | Allows you to specify the usage rights of the images returned when search\_type=images. Valid values are non\_commercial\_reuse\_with\_modification or non\_commercial\_reuse. |
| time\_period | optional | Determines the time period of the results shown. It can be set to last\_hour, last\_day (for the last 24 hours), last\_week (for the last 7 days), last\_month, last\_yearor custom. When using customyou must also specifiy one or both of the time\_period\_minor time\_period\_maxparameters to define the custom time period. |
| time\_period\_min | optional | Determines the minimum (i.e. 'from') time to use when time\_periodis set to custom. Should be in the form MM/DD/YYYY, I.e. for 31st December 2018 time\_period\_minwould be 12/31/2018. |
| time\_period\_max | optional | Determines the maximum (i.e. 'to') time to use when time\_periodis set to custom. Should be in the form MM/DD/YYYY, I.e. for 31st December 2018 time\_period\_maxwould be 12/31/2018. |
| safe | optional | Determines whether Safe Searchis enabled for the results. Can be set to activeto enable Safe Search, or off to disable Safe Search. |
| tbs | optional | Sets a specific string to be added to the Google tbs parameter in the underlying Google query. The tbs parameter is normally generated automatically by the API, but it can be set explicitly also. |
Next Steps

* [Google Image Results](/docs/search-api/results/google/images)

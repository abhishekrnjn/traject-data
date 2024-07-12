Google Shopping Parameters
--------------------------

GET`/search?engine=google&search_type=shopping`The Google Shopping Parameters are applicable when making a request with `search_type=shopping` to retrieve Shopping results for a given search term. The search term is specified in the `q` parameter and the optional `location` parameter can be used to geo-locate the shopping request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

![]()Google Shopping ResultsFor example, to request shopping results for the keyword `pizza` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=shopping&q=pizza&location=United+States
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d q="pizza" \
-d search_type="shopping" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  search_type: "shopping",
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
  'search_type': 'shopping',
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
  'search_type' => 'shopping',
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

Copy### Google Shopping Parameters

The following parameters are available for all requests made when `search_type=shopping`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=trends. |
| q | required | The keyword you want to use to perform the Shopping search. |
| location | optional | Determines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the SerpWow built-in locations then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the location\_autoparameter). |
| location\_auto | optional | If the locationfield is set to a SerpWow built-in location from the Locations API, and location\_autois set to true (default) then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location. Valid values are true (default) to enable this behaviour or falseto disable. |
| uule | optional | The Google UULE parameter - use to pass through a custom uule parameter to Google. SerpWow automatically generates the uule when you use the location parameter but we allow you to overwrite it directly by specifying a uule directly. |
| google\_domain | optional | The Google domain to use to run the search query. View the full list of supported google\_domainvalues here. Defaults to google.com. |
| gl | optional | The gl parameter determines the Google country to use for the query. View the full list of supported glvalues here. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. |
| page | optional | Determines the page of results to return, defaults to 1. Use in combination with the num parameter to implement pagination. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
| num | optional | Determines the number of results to show per page. Use in combination with the page parameter to implement pagination.Note the num parameter is not always honoured by Google for search\_type=shopping requests. When using the num parameter you are requesting that number of results per page. There is no guarantee that that number of results will necessarily be served. |
| sort\_by | optional | Sets the sort ordering of the shopping results returned. Valid values are:relevanceSort shopping results by relevance to the search term supplied in the q parameter, the default.price\_low\_to\_highSort shopping results by lowest to highest price.price\_high\_to\_lowSort shopping results by highest to lowest price.review\_scoreSort shopping results by review score, highest review score first. |
| shopping\_buy\_on\_google | optional | Determines whether the "Buy on Google" option is selected when running a search\_type=shopping search. Valid values are true or false. |
| shopping\_filter | optional | A shopping filter (i.e. "Brand") to filter the results to. Shopping filter values are returned in the filters property of the shopping response. |
| shopping\_price\_min | optional | The minimum price of products. For example shopping\_price\_min=4.99 |
| shopping\_price\_max | optional | The maximum price of products returned. For example shopping\_price\_max=29.99 |
| shopping\_condition | optional | The condition of products returned. Can be set to new or used. |
| shopping\_merchants | optional | A comma-separated list of merchant IDs to retrieve shopping results. Merchant ID's can be found in the merchagg: section of any Google Shopping URL. |
Next Steps

* [Google Shopping Results](/docs/search-api/results/google/shopping)

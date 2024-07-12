Google News Parameters
----------------------

GET`/search?engine=google&search_type=news`The Google News Parameters are applicable when making a request with `search_type=news` to retrieve news results for a given search term. The search term is specified in the `q` parameter and the optional `location` parameter can be used to geo-locate the news request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

You can use the `time_period` request parameter to refine your news search to specific time periods.

If you wish to exclude news results where Google have modified the original query set `exclude_if_modified=true` in your request parameters.

![]()Google News ResultsFor example, to request news results for the keyword `pizza` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=news&q=pizza&location=United+States
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d q="pizza" \
-d search_type="news" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  search_type: "news",
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
  'search_type': 'news',
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
  'search_type' => 'news',
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

Copy### Google News Parameters

The following parameters are available for all requests made when `search_type=news`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=news. |
| q | required | The keyword you want to use to perform the News search. |
| location | optional | Determines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the SerpWow built-in locations then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the location\_autoparameter). |
| location\_auto | optional | If the locationfield is set to a SerpWow built-in location from the Locations API, and location\_autois set to true (default) then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location. Valid values are true (default) to enable this behaviour or falseto disable. |
| uule | optional | The Google UULE parameter - use to pass through a custom uule parameter to Google. SerpWow automatically generates the uule when you use the location parameter but we allow you to overwrite it directly by specifying a uule directly. |
| google\_domain | optional | The Google domain to use to run the search query. View the full list of supported google\_domainvalues here. Defaults to google.com. |
| gl | optional | The gl parameter determines the Google country to use for the query. View the full list of supported glvalues here. Defaults to us. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
| lr | optional | The lr parameter limits the results to websites containing the specified language. View the full list of supported lrvalues here. |
| cr | optional | The cr parameter instructs Google to limit the results to websites in the specified country. View the full list of supported crvalues here. |
| time\_period | optional | Determines the time period of the results shown. It can be set to last\_hour, last\_day (for the last 24 hours), last\_week (for the last 7 days), last\_month, last\_yearor custom. When using customyou must also specifiy one or both of the time\_period\_minor time\_period\_maxparameters to define the custom time period. |
| time\_period\_min | optional | Determines the minimum (i.e. 'from') time to use when time\_periodis set to custom. Should be in the form MM/DD/YYYY, I.e. for 31st December 2018 time\_period\_minwould be 12/31/2018. |
| time\_period\_max | optional | Determines the maximum (i.e. 'to') time to use when time\_periodis set to custom. Should be in the form MM/DD/YYYY, I.e. for 31st December 2018 time\_period\_maxwould be 12/31/2018. |
| nfpr | optional | Determines whether to exclude results from auto-corrected queries that were spelt wrong. Can be set to 1to exclude auto-corrected results, or 0 (default) to include them. |
| filter | optional | Determines if the filters for Similar Resultsand Omitted Resultsare on or off. Can be set to 1 (default) to enable these filters, or 0to disable these filters. |
| safe | optional | Determines whether Safe Searchis enabled for the results. Can be set to activeto enable Safe Search, or off to disable Safe Search. |
| page | optional | Determines the page of results to return, defaults to 1. Use in combination with the num parameter to implement pagination. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
| num | optional | Determines the number of results to show per page. Use in combination with the page parameter to implement pagination. The maximum number of news results Google return per request is 100. |
| tbs | optional | Sets a specific string to be added to the Google tbs parameter in the underlying Google query. The tbs parameter is normally generated automatically by the API, but it can be set explicitly also. |
| sort\_by | optional | Determines how results are sorted, valid values are relevance or date. Note that when sort\_by=date the show\_duplicates parameter can be used. |
| show\_duplicates | optional | Determines whether duplicates are shown in the news results. Must be used in conjunction with the sort\_by parameter where sort\_by is set to date. Valid values are true or false. Defaults to false. |
| exclude\_if\_modified | optional | Determines whether the news\_results returned when Google modifies the original query. Set to true to exclude news\_results when Google modifies the original query or false (the default) to include news\_results when Google modifies the original query. |
Next Steps

* [Google News Results](/docs/search-api/results/google/news)

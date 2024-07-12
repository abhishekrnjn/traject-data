Google Search Parameters
------------------------

GET`/search?engine=google`The Google Search Parameters are applicable when making a request with `engine=google` to retrieve Google search results for a given search term. The search term is specified in the `q` parameter. The location your search is run from is determined by the `location` parameter, which can be populated with a `full_name` or `gps_coordinates` value from the [Locations API](/docs/locations-api).

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Search ResultsFor example, to request videos results for the keyword `pizza` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&q=pizza&location=United+States
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d q="pizza" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
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

Copy### Google Search Parameters

The following parameters are available for Google Search requests:

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| q | required | The keyword you want to use to perform the search. |
| location | optional | Determines the geographic location in which the query is executed.You can enter any location as free-text, but if you choose one of the SerpWow built-in locations then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the location\_autoparameter).To get results based on latitude and longitude coordinates you should specify your location parameter in the form location=lat:43.437677,lon:-3.8392765 where 43.437677 is your latitude value and -3.8392765 is your longitude value. The gland hlparameters are not automatically updated when using this format. |
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
| num | optional | Determines the number of results to show per page. Use in combination with the page parameter to implement pagination |
| tbs | optional | Sets a specific string to be added to the Google tbs parameter in the underlying Google query. The tbs parameter is normally generated automatically by the API, but it can be set explicitly also. |
| knowledge\_graph\_id | optional | The knowledge\_graph\_id request parameter sets the kgmid Google parameter. You can use this to prompt a specific knowledge graph to show in the results, an example would be knowledge\_graph\_id=/m/0jg24 |
| flatten\_results | optional | Can be set to true or false. Determines whether SerpWow flattens the inline\_videos, inline\_images, inline\_tweets, top\_storiesand local\_resultsand shows them inline with the organic\_results. This is useful if you want a simplified list of all of the results shown for an organic web search, irrespective of the type of result. When flatten\_results=true then a new property type is added to each item in the organic\_results array indicating the type of result (i.e. "ad", "inline\_tweets" etc). |
| include\_answer\_box | optional | Determines whether to include the answer box (sometimes called the "featured snippet") in the organic\_results array and treat it as the first result. This may be desirable if you treat the result Bing displayed in the answer\_box as the first organic result. |
| include\_advertiser\_info | optional | Retrieve the "advertiser info" for Ads (where published, it's not published on all Ads) by setting include\_advertiser\_info=true. Advertiser info gives the company name of the company running the Ad.Note that requesting advertiser info consumes 2 credits (instead of the normal 1 credit) as additional internal requests are required. |
| include\_ai\_overview\_check | optional | Determines if the AI Overview is generated on the serach results page. NOTE: This only checks for search results where the requestor is NOT logged into a Google account. |
Next Steps

* [Google Search Results](/docs/search-api/results/google/search)

Google Search Parameters
------------------------

GET`/search`The Google Search Parameters are applicable when making a request to the Search API to retrieve Google search results for a given search term. The search term is specified in the `q` parameter. The location your search is run from is determined by the `location` parameter, which can be populated with a `full_name` or `gps_coordinates` value from the [Locations API](/docs/locations-api).

![](https://apiimages.imgix.net/scaleserp/images/png/docs/google_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Search ResultsFor example, to request videos results for the keyword `pizza` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&q=pizza&location=United+States
```

```
curl -L --get https://api.scaleserp.com/search \
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
Copy### Google Search Parameters

The following parameters are available for Google Search requests:

ParameterRequiredDescriptionqrequiredThe keyword you want to use to perform the search.locationoptionalDetermines the geographic location in which the query is executed.  
  
You can enter any location as free-text, but if you choose one of the Scale SERP [built-in locations](/docs/locations-api) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the `location_auto`parameter).  
  
To get results based on latitude and longitude coordinates you should specify your `location` parameter in the form `location=lat:43.437677,lon:-3.8392765` where `43.437677` is your latitude value and `-3.8392765` is your longitude value. The `gl`and `hl`parameters are not automatically updated when using this format.location\_autooptionalIf the `location`field is set to a Scale SERP [built-in location](/docs/locations-api) from the [Locations API](/docs/locations-api), and `location_auto`is set to `true` (default) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location. Valid values are `true` (default) to enable this behaviour or `false`to disable.uuleoptionalThe Google UULE parameter - use to pass through a custom `uule` parameter to Google. Scale SERP automatically generates the `uule` when you use the `location` parameter but we allow you to overwrite it directly by specifying a `uule` directly.google\_domainoptionalThe Google domain to use to run the search query. View the full list of supported `google_domain`values [here](/docs/search-api/reference/google-domains). Defaults to `google.com`.gloptionalThe `gl` parameter determines the Google country to use for the query. View the full list of supported `gl`values [here](/docs/search-api/reference/google-countries). Defaults to `us`.hloptionalThe `hl` parameter determines the Google UI language to return results. View the full list of supported `hl`values [here](/docs/search-api/reference/google-languages). Defaults to `en`.lroptionalThe `lr` parameter limits the results to websites containing the specified language. View the full list of supported `lr`values [here](/docs/search-api/reference/google-lr-languages).croptionalThe `cr` parameter instructs Google to limit the results to websites in the specified country. View the full list of supported `cr`values [here](/docs/search-api/reference/google-cr-countries).time\_periodoptionalDetermines the time period of the results shown. It can be set to `last_hour`, `last_day` (for the last 24 hours), `last_week` (for the last 7 days), `last_month`, `last_year`or `custom`. When using `custom`you must also specifiy one or both of the `time_period_min`or `time_period_max`parameters to define the custom time period.time\_period\_minoptionalDetermines the minimum (i.e. 'from') time to use when `time_period`is set to `custom`. Should be in the form `MM/DD/YYYY`, I.e. for 31st December 2018 `time_period_min`would be `12/31/2018`.time\_period\_maxoptionalDetermines the maximum (i.e. 'to') time to use when `time_period`is set to `custom`. Should be in the form `MM/DD/YYYY`, I.e. for 31st December 2018 `time_period_max`would be `12/31/2018`.nfproptionalDetermines whether to exclude results from auto-corrected queries that were spelt wrong. Can be set to `1`to exclude auto-corrected results, or `0` (default) to include them.filteroptionalDetermines if the filters for `Similar Results`and `Omitted Results`are on or off. Can be set to `1` (default) to enable these filters, or `0`to disable these filters.safeoptionalDetermines whether `Safe Search`is enabled for the results. Can be set to `active`to enable Safe Search, or `off` to disable Safe Search.pageoptionalDetermines the page of results to return, defaults to `1`. Use in combination with the `num` parameter to implement pagination.max\_pageoptionalUse the `max_page` parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.  
  
See the [Pagination](/docs/search-api/pagination) docs for more information.numoptionalDetermines the number of results to show per page. Use in combination with the `page` parameter to implement paginationtbsoptionalSets a specific string to be added to the Google `tbs` parameter in the underlying Google query. The `tbs` parameter is normally generated automatically by the API, but it can be set explicitly also.knowledge\_graph\_idoptionalThe `knowledge_graph_id` request parameter sets the `kgmid` Google parameter. You can use this to prompt a specific knowledge graph to show in the results, an example would be `knowledge_graph_id=/m/0jg24`flatten\_resultsoptionalCan be set to `true` or `false`. Determines whether Scale SERP flattens the `inline_videos`, `inline_images`, `inline_tweets`, `top_stories`and `local_results`and shows them inline with the `organic_results`. This is useful if you want a simplified list of all of the results shown for an organic web search, irrespective of the type of result. When `flatten_results=true` then a new property `type` is added to each item in the `organic_results` array indicating the type of result (i.e. "ad", "inline\_tweets" etc).include\_answer\_boxoptionalDetermines whether to include the answer box (sometimes called the "featured snippet") in the `organic_results` array and treat it as the first result. This may be desirable if you treat the result Bing displayed in the `answer_box` as the first organic result.include\_advertiser\_infooptionalRetrieve the "advertiser info" for Ads (where published, it's not published on all Ads) by setting `include_advertiser_info=true`. Advertiser info gives the company name of the company running the Ad.  
  
**Note** that requesting advertiser info consumes 2 credits (instead of the normal 1 credit) as additional internal requests are required.  
  
![]()Next Steps

* [Google Search Results](/docs/search-api/results/google/search)

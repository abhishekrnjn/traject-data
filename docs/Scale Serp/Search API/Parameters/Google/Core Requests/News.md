Google News Parameters
----------------------

GET`/search?search_type=news`The Google News Parameters are applicable when making a request with `search_type=news` to retrieve news results for a given search term. The search term is specified in the `q` parameter and the optional `location` parameter can be used to geo-locate the news request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

You can use the `time_period` request parameter to refine your news search to specific time periods.

If you wish to exclude news results where Google have modified the original query set `exclude_if_modified=true` in your request parameters.

![]()Google News ResultsFor example, to request news results for the keyword `pizza` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&search_type=news&q=pizza&location=United+States
```

```
curl -L --get https://api.scaleserp.com/search \
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
  'search_type': 'news',
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
  'search_type' => 'news',
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
Copy### Google News Parameters

The following parameters are available for all requests made when `search_type=news`.

ParameterRequiredDescriptionsearch\_typerequiredShould be set to `search_type=news`.qrequiredThe keyword you want to use to perform the News search.locationoptionalDetermines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the Scale SERP [built-in locations](/docs/locations-api) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the `location_auto`parameter).location\_autooptionalIf the `location`field is set to a Scale SERP [built-in location](/docs/locations-api) from the [Locations API](/docs/locations-api), and `location_auto`is set to `true` (default) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location. Valid values are `true` (default) to enable this behaviour or `false`to disable.uuleoptionalThe Google UULE parameter - use to pass through a custom `uule` parameter to Google. Scale SERP automatically generates the `uule` when you use the `location` parameter but we allow you to overwrite it directly by specifying a `uule` directly.google\_domainoptionalThe Google domain to use to run the search query. View the full list of supported `google_domain`values [here](/docs/search-api/reference/google-domains). Defaults to `google.com`.gloptionalThe `gl` parameter determines the Google country to use for the query. View the full list of supported `gl`values [here](/docs/search-api/reference/google-countries). Defaults to `us`.hloptionalThe `hl` parameter determines the Google UI language to return results. View the full list of supported `hl`values [here](/docs/search-api/reference/google-languages). Defaults to `en`.lroptionalThe `lr` parameter limits the results to websites containing the specified language. View the full list of supported `lr`values [here](/docs/search-api/reference/google-lr-languages).croptionalThe `cr` parameter instructs Google to limit the results to websites in the specified country. View the full list of supported `cr`values [here](/docs/search-api/reference/google-cr-countries).time\_periodoptionalDetermines the time period of the results shown. It can be set to `last_hour`, `last_day` (for the last 24 hours), `last_week` (for the last 7 days), `last_month`, `last_year`or `custom`. When using `custom`you must also specifiy one or both of the `time_period_min`or `time_period_max`parameters to define the custom time period.time\_period\_minoptionalDetermines the minimum (i.e. 'from') time to use when `time_period`is set to `custom`. Should be in the form `MM/DD/YYYY`, I.e. for 31st December 2018 `time_period_min`would be `12/31/2018`.time\_period\_maxoptionalDetermines the maximum (i.e. 'to') time to use when `time_period`is set to `custom`. Should be in the form `MM/DD/YYYY`, I.e. for 31st December 2018 `time_period_max`would be `12/31/2018`.nfproptionalDetermines whether to exclude results from auto-corrected queries that were spelt wrong. Can be set to `1`to exclude auto-corrected results, or `0` (default) to include them.filteroptionalDetermines if the filters for `Similar Results`and `Omitted Results`are on or off. Can be set to `1` (default) to enable these filters, or `0`to disable these filters.safeoptionalDetermines whether `Safe Search`is enabled for the results. Can be set to `active`to enable Safe Search, or `off` to disable Safe Search.pageoptionalDetermines the page of results to return, defaults to `1`. Use in combination with the `num` parameter to implement pagination.max\_pageoptionalUse the `max_page` parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.  
  
See the [Pagination](/docs/search-api/pagination) docs for more information.numoptionalDetermines the number of results to show per page. Use in combination with the `page` parameter to implement pagination. The maximum number of news results Google return per request is 100.tbsoptionalSets a specific string to be added to the Google `tbs` parameter in the underlying Google query. The `tbs` parameter is normally generated automatically by the API, but it can be set explicitly also.sort\_byoptionalDetermines how results are sorted, valid values are `relevance` or `date`. Note that when `sort_by=date` the `show_duplicates` parameter can be used.show\_duplicatesoptionalDetermines whether duplicates are shown in the news results. Must be used in conjunction with the `sort_by` parameter where `sort_by` is set to `date`. Valid values are `true` or `false`. Defaults to `false`.exclude\_if\_modifiedoptionalDetermines whether the `news_results` returned when Google modifies the original query. Set to `true` to exclude `news_results` when Google modifies the original query or `false` (the default) to include `news_results` when Google modifies the original query.Next Steps

* [Google News Results](/docs/search-api/results/google/news)

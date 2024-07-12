Google Trends Parameters
------------------------

GET`/search?engine=google&search_type=trends`The Google Trends Parameters are applicable when making a request with `search_type=trends` to retrieve Google Trends results for a given search term. The search term is specified in the `q` parameter.

  
:::hint



**Localizing Google Trends Requests**  
To localize Trends requests you should use the `trends_geo` request parameter. For a list of all available `trends_geo` values see the [Trends Geo Reference](/docs/search-api/reference/google-trends-geos).  
:::

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_trends.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Trends Results  
:::hint



**Multiple Trends Keywords**  
You can request comparative Trends results for up to 5 keywords in one request. Specify multiple trends keywords in comma-seperated notation in the `q` parameter. For example, to replicate the request shown in the screenshot below the `q` parameter would be `q=pizza,burger,chips,sausages,bread`.  
  
![]()  
:::

To request Trends results for the keyword `pizza`, worldwide (i.e. without a `trends_geo` parameter), the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=trends&q=pizza
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d q="pizza" \
-d search_type="trends"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  search_type: "trends"
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
  'search_type': 'trends'
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
  'search_type' => 'trends'
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

Copy### Google Trends Parameters

The following parameters are available for all requests made when `search_type=trends`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=trends. |
| q | required | The keyword you want to use to perform the Trends search. You can request up to 5 Trends keywords to compare in one request. To specify multiple keywords, seperate each with a comma - i.e. q=dog,cat. |
| gl | optional | The gl parameter determines the Google country to use for the query. View the full list of supported glvalues here. Defaults to us. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
| time\_period | optional | Determines the time period of the results shown. It can be set to last\_hour, last\_day (for the last 24 hours), last\_week (for the last 7 days), last\_month, last\_yearor custom. When using customyou must also specifiy one or both of the time\_period\_minor time\_period\_maxparameters to define the custom time period. |
| time\_period\_min | optional | Determines the minimum (i.e. 'from') time to use when time\_periodis set to custom. Should be in the form MM/DD/YYYY, I.e. for 31st December 2018 time\_period\_minwould be 12/31/2018. |
| time\_period\_max | optional | Determines the maximum (i.e. 'to') time to use when time\_periodis set to custom. Should be in the form MM/DD/YYYY, I.e. for 31st December 2018 time\_period\_maxwould be 12/31/2018. |
| trends\_type | optional | Determines the Google property to search for Trends data. Valid values are web, images, news, youtube or shopping. |
| trends\_resolution | optional | Determines the resolution requested for the trends\_interest\_by\_subregion section of SerpWow's Google Trends results. Valid values are country, city, dma or region. |
| trends\_geo | optional | A Google Trends Geo ID - typically a 2-letter country code, for example trends\_geo=DE for Trends data for Germany. Can also specify a more specific trends\_geo for a specific location within a country. View the full list of supported trends\_geo values here.Omit the trends\_geo parameter entirely if you wish to run your query as "worldwide". |
| trends\_category | optional | A Google Trends Category ID. View the full list of supported trends\_category values here. |
Next Steps

* [Google Trends Results](/docs/search-api/results/google/trends)

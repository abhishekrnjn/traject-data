Common Parameters
-----------------

GET`/search`The following parameters are used to configure your Search API request. They should be appended as querystring parameters to the Search API`GET`HTTP request.

The parameters below are **common** to all Search API requests regardless of the `engine` chosen.

SerpWow lets you search [Google](/docs/search-api/searches/google/search), [Bing](/docs/search-api/searches/bing/search), [Yahoo](/docs/search-api/searches/yahoo/search), [Baidu](/docs/search-api/searches/baidu/search), [Yandex](/docs/search-api/searches/yandex/search), [Naver](/docs/search-api/searches/naver/search), [Amazon](/docs/search-api/searches/amazon/search) or [Ebay](/docs/search-api/searches/ebay/search) by specifying the `engine` parameter.

An example request is below:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&q=pizza&location=United+States
```

```
$ curl --get https://api.serpwow.com/live/search \
          -d api_key="demo" \
          -d q="pizza" \
          -d location="United States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  location: "United States"
}

// make the http GET request to SerpWow
axios.get('https://api.serpwow.com/live/search', { params })
  .then(response => {

    // print the JSON response from SerpWow
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
  'location': 'United States'
}

# make the http GET request to SerpWow
api_result = requests.get('https://api.serpwow.com/live/search', params)

# print the JSON response from SerpWow
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'pizza',
  'location' => 'United States'
]);

# make the http GET request to SerpWow
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

# print the JSON response from SerpWow
echo $api_result;
```
  
:::::

Copy| Parameter | Required | Description |
| --- | --- | --- |
| api\_key | required | The API key for your SerpWow account. |
| engine | optional | The search engine to use, valid values are google, bing, yahoo, baidu, yandex, naver or amazon. Defaults to google. |
| search\_type | optional | The type of request to make. The value of the type parameter determines which additional parameters are available. For example, if you make a request with search\_type=news then additional Google News Parameters, specific to news requests, are available.Valid values for search\_type are:| Google Requests | The following search\_type values are available when engine=google: |
| --- | --- |
(not set)If the search\_type parameter is omitted then a regular web search is performed. See additional Google Search Parameters.newsPerform a Google News request. See additional See additional Google News Parameters.imagesPerform a Google Images request. See additional See additional Google Images Parameters.videosPerform a Google Videos request. See additional See additional Google Videos Parameters.scholarPerform a Google Scholar request. See additional See additional Google Scholar Parameters.reverse\_image\_searchPerform a Google Reverse Image Search request. See additional See additional Google Reverse Image Parameters.trendsPerform a Google Trends request. See additional See additional Google Trends Parameters.autocompletePerform a Google Autocomplete request. See additional See additional Google Autocomplete Parameters.placesPerform a Google Places request. See additional See additional Google Places Parameters.place\_detailsPerform a Google Place Details request to get further information on a given Place. See additional See additional Google Place Details Parameters.place\_photosPerform a Google Place Photos request to get Place Photos for a given Place. See additional See additional Google Place Photos Parameters.place\_reviewsPerform a Google Place Reviews request to get Place Reviews for a given Place. See additional See additional Google Place Reviews Parameters.place\_productsPerform a Google Place Products request to get Place Products for a given Place. See additional See additional Google Place Products Parameters.place\_postsPerform a Google Place Posts request to get Place Posts for a given Place. See additional See additional Google Place Posts Parameters.shoppingPerform a Google Shopping search results. See additional See additional Google Shopping Parameters.productPerform a Google Product results for a single product. See additional See additional Google Product Parameters.Note that when making a search\_type=product request the product\_type parameter determines the type of Product request, available values for product\_type are:reviewsRetrieve reviews for a given Product. See additional See additional Google Product Reviews Parametersonline\_sellersRetrieve sellers for a given Product. See additional See additional Google Product Online Sellers ParametersspecificationsRetrieve data from the specifications page for a given Product. See additional See additional Google Product Specifications Parameters| Bing Requests | The following search\_type values are available when engine=bing: |
| --- | --- |
(empty)If the search\_type parameter is omitted, then a regular web search is performed. See additional Bing Search Parameters.newsPerform a Bing News request. See additional See additional Bing News Parameters.imagesPerform a Bing Images request. See additional See additional Bing Images Parameters.| Yahoo Requests | The following search\_type values are available when engine=yahoo: |
| --- | --- |
(empty)If the search\_type parameter is omitted, then a regular web search is performed. See additional Yahoo Search Parameters.newsPerform a Yahoo News request. See additional See additional Yahoo News Parameters.| Baidu Requests | The following search\_type values are available when engine=baidu: |
| --- | --- |
(empty)If the search\_type parameter is omitted, then a regular web search is performed. See additional Baidu Search Parameters.| Yandex Requests | The following search\_type values are available when engine=yandex: |
| --- | --- |
(empty)If the search\_type parameter is omitted, then a regular web search is performed. See additional Yandex Search Parameters.| Naver Requests | The following search\_type values are available when engine=naver: |
| --- | --- |
(empty)If the search\_type parameter is omitted, then a regular web search is performed. See additional Naver Search Parameters.newsPerform a Naver News request. See additional See additional Naver News Parameters.| Amazon Requests | The following search\_type values are available when engine=amazon: |
| --- | --- |
(empty)If the search\_type parameter is omitted, then a regular web search is performed. See additional Amazon Search Parameters.| Ebay Requests | The following search\_type values are available when engine=ebay: |
| --- | --- |
(empty)If the search\_type parameter is omitted, then a regular web search is performed. See additional Ebay Search Parameters. |
| url | optional | Specifies the URL to open (instead of specifying a query using the q parameter). The url parameter can be a free-form URL from the target site (as specified in the engine parameter).Note To specify the type of parsing applied to the results from the url parameter, use the search\_type parameter.Note The url parameter must be URL-encoded. The url parameter is not available for all search\_type values. |
| device | optional | Determines the device to use to get results.Can be set to desktop (default) to use a regular desktop web browser, tablet to use a tablet browser (use the tablet\_type to choose the type of tablet device), or mobile to use a mobile browser (use the mobile\_type to choose the type of mobile device).Note that not all search\_type values are parsed for each device (for example, some results are parsed in desktop only), see the individual results for more information. |
| mobile\_type | optional | Applies when device=mobile and determines the type of mobile device used to get results.Can be set to iphone for an iPhone mobile device, or android for an Android mobile device. |
| tablet\_type | optional | Applies when device=tablet and determines the type of tablet device used to get results.Can be set to ipad for an iPad device, or android for an Android tablet device. |
| output | optional | Determines the format in which results are returned. Can be set to json (default) to get the results as structured JSON, html to get the raw html retrieved or csvto return the results in CSV format. When using csvyou can also use the csv\_fields parameter to specify which fields to return in the CSV. |
| csv\_fields | optional | Determines the fields that are returned when returning in csv mode (i.e. when the output parameter is set to csv). Should be specified as a comma seperated list of fields (in nested field, dot notation, format). For more information on the csv\_fieldsparameter please see the CSV Fields Reference. |
| include\_html | optional | Determines whether raw HTML is included in the response (this can increase the size of the response). Can be set to true or false (the default).Note When adding searches with include\_html=true to a Batch the maximum number of searches is lower (100) because including the HTML within the response makes the Batch Result Sets much larger. The limit is in place to ensure Result Set files are of a manageable size. If you have need to run a large number of searches all with include\_html=true then simply split the searches across multiple 100-search Batches. |
| skip\_on\_incident | optional | Instructs the API to not serve requests when a parsing incident is detected. Valid values are all (where the API will not serve a response if a "degraded" or "major" parsing incident is live) and major\_only (where the API will not serve a response is a "major" parsing incident is live, but will if a "degraded service" parsing incident is live).You can view service status via the status page.Using skip\_on\_incident can be desirable if your system is making unsupervised requests to the API that you would like to gracefully fail in the event of an incident. |
| hide\_base64\_images | optional | Instructs the API to not include Base64 images in the response. Base64-encoded images from SERP pages can increase the size of the response considerably so sometimes it's desirable to have them excluded from the API response.Note that this parameter is set to hide\_base64\_images=true by default when using Batches (to minimise the size of the Batch Result Sets). |
| cookie | optional | The cookie string to send along with the request. Should be URL-encoded. Use this parameter to send custom cookies along with the request made. It will be sent in the cookie HTTP Header made by the platform. |
| include\_fields | optional | A comma-seperated list JSON field names to include in the JSON object the API returns. You can specify the field names in dot notation - i.e. include\_fields=pagination will only include the the pagination property in the response JSON. Use include\_fields if you only want to include specific fields in the API's JSON response. |
| exclude\_fields | optional | A comma-seperated list of JSON field names to exclude from the JSON object the API returns. You can specify the field names in dot notation - i.e. exclude\_fields=pagination will remove the pagination property from the response JSON. Use exclude\_fields if there are specific fields you wish to exclude from the API's JSON response. |
Next Steps

* [Google Parameters](/docs/search-api/searches/google/search)
* [Bing Parameters](/docs/search-api/searches/bing/search)
* [Yahoo Parameters](/docs/search-api/searches/yahoo/search)
* [Baidu Parameters](/docs/search-api/searches/baidu/search)
* [Yandex Parameters](/docs/search-api/searches/yandex/search)
* [Naver Parameters](/docs/search-api/searches/naver/search)
* [Amazon Parameters](/docs/search-api/searches/amazon/search)
* [Ebay Parameters](/docs/search-api/searches/ebay/search)

Google Product Online Sellers Parameters
----------------------------------------

GET`/search?search_type=product&product_type=sellers_online`The Google Product Online Sellers Parameters are applicable when making a request with `search_type=product` and `product_type=sellers_online` to retrieve product online sellers results for a given product ID. The product ID is specified in the `product_id` parameter and you should also specify a `location` parameter to geo-locate the request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

Google Product IDs are returned by [Google Shopping search](/docs/search-api/results/google/shopping) requests.



**Products & Location**  
Google Product pages are highly location-sensitive so it is important that you specify a `location` that matches the location that was used to retrieve the `product_id` in the original [Google Shopping search](/docs/search-api/searches/google/shopping) request.![]()Google Product Online Sellers ResultsFor example, to request product online sellers results for the product ID `12094323291759970870` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&search_type=product&product_type=sellers_online&product_id=12094323291759970870&location=United+States
```

```
curl -L --get https://api.scaleserp.com/search \
-d api_key="demo" \
-d product_id="12094323291759970870" \
-d search_type="product" \
-d product_type="sellers_online" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  product_id: "12094323291759970870",
  search_type: "product",
  product_type: "sellers_online",
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
  'product_id': '12094323291759970870',
  'search_type': 'product',
  'product_type': 'sellers_online',
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
  'product_id' => '12094323291759970870',
  'search_type' => 'product',
  'product_type' => 'sellers_online',
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
Copy### Google Product Online Sellers Parameters

The following parameters are available for all requests made when `search_type=product` and `product_type=sellers_online`.

ParameterRequiredDescriptionsearch\_typerequiredShould be set to `search_type=product`.product\_typerequiredShould be set to `product_type=sellers_online`.product\_idrequiredThe Google Product ID to retrieve. Google Product IDs are returned by [Google Shopping search](/docs/search-api/results/google/shopping) requests.sort\_byoptionalSets the sort ordering of the product online sellers returned. Valid values are:base\_price  
Sort product online sellers results by base price.  
total\_price  
Sort product online sellers results by total price.  
promotion  
Sort product online sellers results by current promotion deals (special offers).  
seller\_rating  
Sort product online sellers results by seller rating (high to low).  
product\_free\_shippingoptionalDetermines whether to filter to only products with free shipping. Valid values are `true` or `false`.product\_condition\_newoptionalDetermines whether to filter to only new (non-used) products. Valid values are `true` or `false`.product\_condition\_usedoptionalDetermines whether to filter to only used (non-new) products. Valid values are `true` or `false`.locationoptionalDetermines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the Scale SERP [built-in locations](/docs/locations-api) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the `location_auto`parameter).location\_autooptionalIf the `location`field is set to a Scale SERP [built-in location](/docs/locations-api) from the [Locations API](/docs/locations-api), and `location_auto`is set to `true` (default) then the `google_domain`, `gl`and `hl`parameters are automatically updated to the domain, country and language that match the built-in location. Valid values are `true` (default) to enable this behaviour or `false`to disable.uuleoptionalThe Google UULE parameter - use to pass through a custom `uule` parameter to Google. Scale SERP automatically generates the `uule` when you use the `location` parameter but we allow you to overwrite it directly by specifying a `uule` directly.google\_domainoptionalThe Google domain to use to run the search query. View the full list of supported `google_domain`values [here](/docs/search-api/reference/google-domains). Defaults to `google.com`.gloptionalThe `gl` parameter determines the Google country to use for the query. View the full list of supported `gl`values [here](/docs/search-api/reference/google-countries). Defaults to `us`.hloptionalThe `hl` parameter determines the Google UI language to return results. View the full list of supported `hl`values [here](/docs/search-api/reference/google-languages). Defaults to `en`.pageoptionalDetermines the page of results to return, defaults to `1`.max\_pageoptionalUse the `max_page` parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.  
  
See the [Pagination](/docs/search-api/pagination) docs for more information.Next Steps

* [Google Product Online Sellers Results](/docs/search-api/results/google/product-online-sellers)

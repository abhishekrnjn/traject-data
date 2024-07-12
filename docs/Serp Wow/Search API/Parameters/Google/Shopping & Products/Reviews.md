Google Product Reviews Parameters
---------------------------------

GET`/search?engine=google&search_type=product&product_type=reviews`The Google Product Reviews Parameters are applicable when making a request with `search_type=product` and `product_type=reviews` to retrieve product reviews results for a given product ID. The product ID is specified in the `product_id` parameter and you should also specify a `location` parameter to geo-locate the request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

Google Product IDs are returned by [Google Shopping search](/docs/search-api/results/google/shopping) requests.

  
:::hint



**Products & Location**  
Google Product pages are highly location-sensitive so it is important that you specify a `location` that matches the location that was used to retrieve the `product_id` in the original [Google Shopping search](/docs/search-api/searches/google/shopping) request.  
:::

  
:::hint



**Place Reviews Pagination**  
Product Reviews results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead, each `product_type=reviews` result will return a `next_page_token` in its' `product_results.pagination` object. This `next_page_token` can be passed in to the `next_page_token` request parameter to retrieve the next page of Product Reviews results.  
:::

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_product_reviews.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Product ReviewsFor example, to request product reviews results for the product ID `13244508647295616715` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=product&product_type=reviews&product_id=13244508647295616715&location=United+States
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d product_id="13244508647295616715" \
-d search_type="product" \
-d product_type="reviews" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  product_id: "13244508647295616715",
  search_type: "product",
  product_type: "reviews",
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
  'product_id': '13244508647295616715',
  'search_type': 'product',
  'product_type': 'reviews',
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
  'product_id' => '13244508647295616715',
  'search_type' => 'product',
  'product_type' => 'reviews',
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

Copy### Google Product Reviews Parameters

The following parameters are available for all requests made when `search_type=product` and `product_type=reviews`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=product. |
| product\_type | required | Should be set to product\_type=reviews. |
| product\_id | required | The Google Product ID to retrieve. Google Product IDs are returned by Google Shopping search requests. |
| sort\_by | optional | Sets the sort ordering of the product reviews returned. Valid values are:relevanceSort product reviews results by relevance, the default.dateSort product reviews results by date, most recent first. |
| location | optional | Determines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the SerpWow built-in locations then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the location\_autoparameter). |
| location\_auto | optional | If the locationfield is set to a SerpWow built-in location from the Locations API, and location\_autois set to true (default) then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location. Valid values are true (default) to enable this behaviour or falseto disable. |
| uule | optional | The Google UULE parameter - use to pass through a custom uule parameter to Google. SerpWow automatically generates the uule when you use the location parameter but we allow you to overwrite it directly by specifying a uule directly. |
| google\_domain | optional | The Google domain to use to run the search query. View the full list of supported google\_domainvalues here. Defaults to google.com. |
| gl | optional | The gl parameter determines the Google country to use for the query. View the full list of supported glvalues here. Defaults to us. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
| next\_page\_token | optional | Product Reviews results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead, each product\_type=reviews result will return a next\_page\_token in its' product\_results.pagination object. This next\_page\_token can be passed in to the next\_page\_token request parameter to retrieve the next page of Product Reviews results. |
Next Steps

* [Google Product Reviews Results](/docs/search-api/results/google/product-reviews)

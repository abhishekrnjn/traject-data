Google Product Parameters
-------------------------

GET`/search?engine=google&search_type=product`The Google Product Parameters are applicable when making a request with `search_type=product` to retrieve product results for a given product ID. The product ID is specified in the `product_id` parameter and you should also specify a `location` parameter to geo-locate the request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

Google Product IDs are returned by [Google Shopping search](/docs/search-api/results/google/shopping) requests.

  
:::hint



**Products & Location**  
Google Product pages are highly location-sensitive so it is important that you specify a `location` that matches the location that was used to retrieve the `product_id` in the original [Google Shopping search](/docs/search-api/searches/google/shopping) request.  
:::

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_product.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Product ResultsFor example, to request product results for the product ID `13244508647295616715` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=product&product_id=13244508647295616715&location=United+States
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d product_id="13244508647295616715" \
-d search_type="product" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  product_id: "13244508647295616715",
  search_type: "product",
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

Copy### Google Product Parameters

The following parameters are available for all requests made when `search_type=product` and no `product_type` parameter is supplied:

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=product. |
| product\_id | required | The Google Product ID to retrieve. Google Product IDs are returned by Google Shopping search requests. |
| product\_free\_shipping | optional | Determines whether to filter to only products with free shipping. Valid values are true or false. |
| product\_condition\_new | optional | Determines whether to filter to only new (non-used) products. Valid values are true or false. |
| product\_condition\_used | optional | Determines whether to filter to only used (non-new) products. Valid values are true or false. |
| location | optional | Determines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the SerpWow built-in locations then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the location\_autoparameter).Note that Google Product requests are highly location-sensitive. It's important that you set a location parameter for the geographic location in which the product\_id was found. |
| location\_auto | optional | If the locationfield is set to a SerpWow built-in location from the Locations API, and location\_autois set to true (default) then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location. Valid values are true (default) to enable this behaviour or falseto disable. |
| uule | optional | The Google UULE parameter - use to pass through a custom uule parameter to Google. SerpWow automatically generates the uule when you use the location parameter but we allow you to overwrite it directly by specifying a uule directly. |
| google\_domain | optional | The Google domain to use to run the query. View the full list of supported google\_domainvalues here. Defaults to google.com. |
| gl | optional | The gl parameter determines the Google country to use for the query. View the full list of supported glvalues here. Defaults to us. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
Next Steps

* [Google Product Results](/docs/search-api/results/google/product)

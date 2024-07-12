Formats & Editions Parameters
-----------------------------

GET`/request`The Formats & Editions Parameters are applicable when making a request with the `type` [parameter](/docs/product-data-api/parameters/formats-editions) set to `type=formats_editions` Rainforest API will return data from the Formats & Editions popup (typically shown on books and collectables product pages to list all of the ASINs of different formats of the current ASIN) for the product specified in either the `asin` and `amazon_domain` parameters or the `url` parameter. The parameters should be appended as querystring parameters to the Product Data API`GET`HTTP request.

Formats & Editions data is retrieved from the [Formats & Editions popup](https://www.amazon.com/dp/B00B1GBS9O?th=1&psc=1) for a single product on Amazon.

![]()Formats & Editions Page

**Paginating Results**  
Amazon returns 10 Formats & Editions per page. To request more formats & editions issue additional requests incrementing the `page` parameter.  
  
**Note** you should inspect the `pagination.has_next_page` property to determine if another page is available.For example, to request all `page=1` of Formats & Editions listings for the ASIN `B00B1GBS9O` on `amazon.com` the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.rainforestapi.com/request?api_key=demo&type=formats_editions&page=1&amazon_domain=amazon.com&asin=B00B1GBS9O
```

```
curl -L --get https://api.rainforestapi.com/request \
-d api_key="demo" \
-d type="formats_editions" \
-d page="1" \
-d amazon_domain="amazon.com" \ 
-d asin="B00B1GBS9O"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  type: "formats_editions",
  page: "1",
  amazon_domain: "amazon.com",
  asin: "B00B1GBS9O"
}

// make the http GET request to Rainforest API
axios.get('https://api.rainforestapi.com/request', { params })
  .then(response => {

    // print the JSON response from Rainforest API
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
  'type': 'formats_editions',
  'page': '1',
  'amazon_domain': 'amazon.com',
  'asin': 'B00B1GBS9O'
}

# make the http GET request to Rainforest API
api_result = requests.get('https://api.rainforestapi.com/request', params)

# print the JSON response from Rainforest API
print(json.dumps(api_result.json()))
```

```
<?php
      
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'type' => 'formats_editions',
  'page' => '1',
  'amazon_domain' => 'amazon.com',
  'asin' => 'B00B1GBS9O'
]);

# make the http GET request to Rainforest API
$ch = curl_init(sprintf('%s?%s', 'https://api.rainforestapi.com/request', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$api_result = curl_exec($ch);
curl_close($ch);

# print the JSON response from Rainforest API
echo $api_result;

?>
```
Copy### Formats & Editions Parameters

The following parameters are available for all requests made when `type=formats_editions`.

ParameterRequiredDescriptionamazon\_domainoptionalThe Amazon domain to retrieve Formats & Editions for the product specified in the `asin` parameter from. For a full list of supported Amazon domains see [Supported Amazon Domains](/docs/product-data-api/reference/amazon-domains).  
  
**Note**: If the `amazon_domain` and `asin` parameters are supplied then the `url` parameter is ignored.asinoptionalThe Amazon ASIN (product ID) to retrieve Formats & Editions for. Used in combination with the `amazon_domain` parameter.  
  
**Note**: If the `asin` and `amazon_domain` parameters are supplied then the `url` parameter is ignored.urloptionalThe Amazon product-page URL to retrieve Formats & Editions from.  
  
**Note**: If the `url` parameter is supplied then the `amazon_domain` and `asin` parameters are ignored.pageoptionalThe current page of Formats & Editions to retrieve. Inspect the `pagination.has_next_page` property in the [Formats & Editions results](/docs/product-data-api/results/formats-editions) to see whether a next page of results is available.max\_pageoptionalUse the `max_page` parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.  
  
See the [Pagination](/docs/product-data-api/pagination) docs for more information.Next Steps

* [Formats & Editions Results](/docs/product-data-api/results/formats-editions)

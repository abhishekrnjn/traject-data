Sales Estimation Parameters
---------------------------

GET`/request`The Sales Estimation Parameters are applicable when making a request with `type=sales_estimation` to retrieve estimated sales information for a single product on Amazon.



**Important Info on Sales Estimates**  
Rainforest uses an internal algorithm which uses signals from an ASIN's product page, bestseller rank, reviews, search result rankings and known sales datapoints to generate estimated weekly and monthly unit sales volumes.  
  
Rainforest sales estimations should be used as indications of likely sales volumes. They are not an exact science and are best used in an application that requires a broad steer on the likely sales volume for a given ASIN. Rainforest provides no warranty as to the accuracy of the sales estimation figures, or the fitness for purpose for any given use-case. They should be used at your own risk.  
  
**Note** that for some products, typically those with a very low bestseller rank, where insufficient data is available for Rainforest to confidently make a sales estimation prediction, then no sales estimation result will be returned.There are two ways to specify a sales estimation request. You can either supply `asin` and `amazon_domain` parameters or, if you require a more generic sales estimation based on a theoritical product of a certain bestseller rank within a top-level Amazon category, you can supply `bestseller_rank`, `sales_estimation_category` and `amazon_domain` parameters. These two methods are described in detail below.

### Method 1: Sales Estimation for a specific ASIN

If you know the ASIN of the product you wish to retrieve sales estimations for you can specify your sales estimation request using the `asin` and `amazon_domain` parameters. For example, to request sales estimation for ASIN `B07GY4DS42` on `amazon.com` the Rainforest request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.rainforestapi.com/request?api_key=demo&type=sales_estimation&amazon_domain=amazon.com&asin=B07GY4DS42
```

```
curl -L --get https://api.rainforestapi.com/request \
-d api_key="demo" \
-d type="sales_estimation" \
-d amazon_domain="amazon.com" \
-d asin="B07GY4DS42"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  type: "sales_estimation",
  amazon_domain: "amazon.com",
  asin: "B07GY4DS42"
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
  'type': 'sales_estimation',
  'amazon_domain': 'amazon.com',
  'asin': 'B07GY4DS42'
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
  'type' => 'sales_estimation',
  'amazon_domain' => 'amazon.com',
  'asin' => 'B07GY4DS42'
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
CopyWhen specifying your request using the `asin` and `amazon_domain` parameters Rainforest performs the following actions:

1. Retrieves the Bestseller Rank (`2` in the example below) and top-level Amazon category (`Appliances` in the example below) from the Product Detail Page for the specified `asin`.![]()
2. Uses the retrieved bestseller rank and top-level Amazon category to perform a sales estimation prediction.

**Note** if it is not possible to retrieve the bestseller rank from the product page (for example, because it is not shown) Rainforest will not return a sales estimation.

### Method 2: Sales Estimation for an arbitrary Bestseller Rank

If you don't known the ASIN of the product you want to retrieve sales estimation for, or you just wish to retrieve a sales estimation based purely on bestseller rank, you can specify your sales estimation request using the `bestseller_rank`, `sales_estimation_category` and `amazon_domain` parameters. This will cause Rainforest to return a sales estimation based data from other products with a similar bestseller rank in the same top-level Amazon category.

To view the avaialble top-level Amazon categories that can be used with the `sales_estimation_category` parameter see the [Sales Estimation Categories reference](/docs/product-data-api/reference/sales-estimation-category-names).

For example, to request sales estimation for bestseller rank `5`, for top-level Amazon category `Pet Supplies` on `amazon.com` the Rainforest request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.rainforestapi.com/request?api_key=demo&type=sales_estimation&bestseller_rank=5&sales_estimation_category=Pet+Supplies&amazon_domain=amazon.com
```

```
curl -L --get https://api.rainforestapi.com/request \
      -d api_key="demo" \
      -d type="sales_estimation" \
      -d bestseller_rank="5" \
      -d sales_estimation_category="Pet Supplies" \
      -d amazon_domain="amazon.com"
```

```
const axios = require('axios');

      // set up the request parameters
      const params = {
      api_key: "demo",
      type: "sales_estimation",
      bestseller_rank: "5",
      sales_estimation_category: "Pet Supplies",
      amazon_domain: "amazon.com"
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
      'type': 'sales_estimation',
      'bestseller_rank': '5',
      'sales_estimation_category': 'Pet Supplies',
      'amazon_domain': 'amazon.com'
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
      'type' => 'sales_estimation',
      'bestseller_rank' => '5',
      'sales_estimation_category' => 'Pet Supplies',
      'amazon_domain' => 'amazon.com'
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
Copy### Supported Amazon Domains

Rainforest supports retrieving sales estimations for the following Amazon domains.

![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/ca.png)[Canada](https://www.amazon.ca)![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/fr.png)[France](https://www.amazon.fr)![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/de.png)[Germany](https://www.amazon.de)![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/in.png)[India](https://www.amazon.in)![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/it.png)[Italy](https://www.amazon.it)![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/mx.png)[Mexico](https://www.amazon.com.mx)![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/es.png)[Spain](https://www.amazon.es)![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/gb.png)[United Kingdom](https://www.amazon.co.uk)![](https://apiimages.imgix.net/rainforestapi/images/png/flags/24x24/us.png)[United States](https://www.amazon.com)### Sales Estimation Parameters

The following parameters are available for all requests made when `type=sales_estimation`.

ParameterRequiredDescriptionamazon\_domainoptionalThe Amazon domain to retrieve sales estimations from.asinoptionalThe Amazon ASIN (product ID) to retrieve a sales estimation for. Please review the **Method 1** documentation above for the behaviour Rainforest enacts in response to an `asin` being supplied in a Sales Estimation request. When using the `asin` parameter the `amazon_domain` parameter is also required.bestseller\_rankoptionalAn arbitrary bestseller rank to retrieve sales estimation data for. Must be used in combination with the `sales_estimation_category` and `amazon_domain` parameters. Please review the **Method 2** documentation above for the behaviour Rainforest enacts in response to a `bestseller_rank` being supplied in a Sales Estimation request.sales\_estimation\_categoryoptionalThe top-level Amazon category to retrieve sales estimation data from. Must be used in combination with the `bestseller_rank` and `amazon_domain` parameters. Please review the **Method 2** documentation above for the behaviour Rainforest enacts in response to a `sales_estimation_category` being supplied in a Sales Estimation request.  
  
**Note** for a list of valid `sales_estimation_category` values, per Amazon domain, review the [Sales Estimation Categories reference](/docs/product-data-api/reference/sales-estimation-category-names).  
  
**Note** the `sales_estimation_category` parameter is case-sensitive.Next Steps

* [Sales Estimation Results](/docs/product-data-api/results/sales-estimation)
* [Sales Estimation Categories](/docs/product-data-api/reference/sales-estimation-category-names)

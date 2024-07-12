Search Parameters
-----------------

GET`/request`The Search Parameters are applicable when making a request with `type=search` to retrieve search results for an Amazon domain - the Amazon domain is specified using the `amazon_domain` parameter and the search term is specified in the `search_term` parameter. The parameters should be appended as querystring parameters to the Product Data API`GET`HTTP request.

Search results are retrieved from the [search results page](https://www.amazon.com/s?k=memory+cards&s=price-desc-rank) on Amazon.

![](https://apiimages.imgix.net/rainforestapi/images/png/docs/search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Search Results PageFor example, to request search results for the search term "memory cards" sorted by "high to low price", on `amazon.com`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.rainforestapi.com/request?api_key=demo&type=search&amazon_domain=amazon.com&search_term=memory+cards&sort_by=price_high_to_low
```

```
curl -L --get https://api.rainforestapi.com/request \
-d api_key="demo" \
-d type="search" \
-d amazon_domain="amazon.com" \
-d search_term="memory+cards" \
-d sort_by="price_low_to_high"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  type: "search",
  amazon_domain: "amazon.com",
  search_term: "memory cards",
  sort_by: "price_high_to_low"
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
  'type': 'search',
  'amazon_domain': 'amazon.com',
  'search_term': 'memory cards',
  'sort_by': 'price_high_to_low'
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
  'type' => 'search',
  'amazon_domain' => 'amazon.com',
  'search_term' => 'memory cards',
  'sort_by' => 'price_high_to_low'
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
Copy### Search Parameters

The following parameters are available for all requests made when `type=search`.

ParameterRequiredDescriptionamazon\_domainoptionalThe Amazon domain to retrieve search results from. For a full list of supported Amazon domains see [Supported Amazon Domains](/docs/product-data-api/reference/amazon-domains).search\_termoptionalA search term to use to search products.![]()refinementsoptionalA comma-seperated list of refinement values to filter the search results by. These allow you to refine your search by values such as "Reviews rating 4 and over", "price range" and "brand".  
  
Refinement values are returned in the `refinements` array of each `type=search` result. Refinement values are dynamic and change by category area or search term used. If you wish to use refinements you should first issue a `type=search` request without specifying any `refinements` to retrieve a master list of the avaialble refinements for the given category area/search term. You can then cache these refinement values for use on subsequent requests.  
  
For example, to run a `type=search` request specifying two refinements with values `p_85/2470955011` and `p_36/2421886011` the value of the `refinements` parameter would be `refinements=p_85/2470955011,p_36/2421886011`  
  
![]()category\_idoptionalA category ID to limit search results to. You may supply any arbitary value in the `category_id` parameter however we recommend using a category ID returned from the [Categories API](/docs/categories-api/overview) as these are known-good category IDs from Amazon.  
  
Rainforest will use the `category_id` in the following form: `https://**amazon_domain**/s?node=**category_id**`.  
  
**Note** that pagination for **top-level** categories is not supported by the Amazon sites. If you wish to iterate the contents of a category the recommended approach is to pick the lowest level categories to perform your iteration / pagination on.sort\_byoptionalDetermines the sort order of search results to return. Valid values are:  
most\_recentSort search results by newest arrivals.price\_low\_to\_highSort search results by lowest to highest price.price\_high\_to\_lowSort search results by highest to lowest price.featuredSort search results by featured first.average\_reviewSort search results by average customer review.relevanceSort search results by most relevant first.  
Applies only to **Audible** [Amazon Domains](/docs/product-data-api/reference/amazon-domains).bestsellersSort search results by best sellers first.  
Applies only to **Audible** [Amazon Domains](/docs/product-data-api/reference/amazon-domains).running\_time\_ascendingSort search results by shortest running time first, from short to long.  
Applies only to **Audible** [Amazon Domains](/docs/product-data-api/reference/amazon-domains).running\_time\_descendingSort search results by shortest running time first, from long to short.  
Applies only to **Audible** [Amazon Domains](/docs/product-data-api/reference/amazon-domains).title\_ascendingSort search results alphabetically by title from A to Z.  
Applies only to **Audible** [Amazon Domains](/docs/product-data-api/reference/amazon-domains).title\_descendingSort search results alphabetically by title from Z to A.  
Applies only to **Audible** [Amazon Domains](/docs/product-data-api/reference/amazon-domains).![]()exclude\_sponsoredoptionalWhether to exclude sponsored search results (when set to `exclude_sponsored=true`) from the search results returned, or not. Defaults to `false`.pageoptionalThe current page of search results to retrieve. Inspect the `pagination.total_pages` property in the [Search results](/docs/product-data-api/results/search) to see how many pages of search results are available.max\_pageoptionalUse the `max_page` parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.  
  
See the [Pagination](/docs/product-data-api/pagination) docs for more information.urloptionalThe Amazon search results page URL to retrieve search results from. Be sure to URL-encode the `url` parameter.  
  
**Note** the `url` parameter is supplied, the `search_term` parameter cannot be used (as the `url` itself defines the search term used).direct\_searchoptionalBy default Amazon will, if a spelling mistake is suspected in the `search_term`, show search results for the corrected search term.  
  
To disable this behaviour and search for the value in `search_term` directly, without auto-correcting it, set `direct_search=true`.Next Steps

* [Search Results](/docs/product-data-api/results/search)

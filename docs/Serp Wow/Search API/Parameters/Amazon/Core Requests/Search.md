Amazon Search Parameters
------------------------

GET`/search?engine=amazon`The Amazon Search Parameters are applicable when making a request with `engine=amazon` to retrieve Amazon search results for a given search term. The search term is specified in the `q` parameter and the optional `amazon_domain` parameter can be used to specify the Amazon domain used for the request. A full list of supported Amazon domains can be [found here](/docs/search-api/reference/amazon-domains).

![](https://apiimages.imgix.net/serpwow/images/png/docs/amazon_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Amazon Search ResultsFor example, to request Amazon search results for the keyword `playing cards` on `amazon.com`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&engine=amazon&amazon_domain=amazon.com&q=playing+cards
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d engine="amazon" \
-d amazon_domain="amazon.com" \
-d q="playing cards"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  engine: "amazon",
  amazon_domain: "amazon.com",
  q: "playing cards"
}

// make the http GET request
axios.get('https://api.serpwow.com/live/search', { params })
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
  'engine': 'amazon',
  'amazon_domain': 'amazon.com',
  'q': 'playing cards'
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
  'engine' => 'amazon',
  'amazon_domain' => 'amazon.com',
  'q' => 'playing cards'
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

Copy### Amazon Search Parameters

The following parameters are available for all requests made when `engine=amazon`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=amazon. |
| q | required | The keyword you want to use to perform the search. |
| amazon\_domain | optional | The Amazon domain to retrieve search results from. For a full list of supported Amazon domains see Supported Amazon Domains. |
| page | optional | Determines the page of results to return, defaults to 1. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
Next Steps

* [Amazon Search Results](/docs/search-api/results/amazon/search)

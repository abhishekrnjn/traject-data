Ebay Search Parameters
----------------------

GET`/search?engine=ebay`The Ebay Search Parameters are applicable when making a request with `engine=ebay` to retrieve Ebay search results for a given search term. The search term is specified in the `q` parameter and the optional `ebay_domain` parameter can be used to specify the Ebay domain used for the request. A full list of supported Ebay domains can be [found here](/docs/search-api/reference/ebay-domains).

![](https://apiimages.imgix.net/serpwow/images/png/docs/ebay_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Ebay Search ResultsFor example, to request Ebay search results for the keyword `playing cards` on `ebay.com`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&engine=ebay&ebay_domain=ebay.com&q=playing+cards
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d engine="ebay" \
-d ebay_domain="ebay.com" \
-d q="playing cards"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  engine: "ebay",
  ebay_domain: "ebay.com",
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
  'engine': 'ebay',
  'ebay_domain': 'ebay.com',
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
  'engine' => 'ebay',
  'ebay_domain' => 'ebay.com',
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

Copy### Ebay Search Parameters

The following parameters are available for all requests made when `engine=ebay`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=ebay. |
| q | required | The keyword you want to use to perform the search. |
| ebay\_domain | optional | The Ebay domain to retrieve search results from. For a full list of supported Ebay domains see Supported Ebay Domains. |
| page | optional | Determines the page of results to return, defaults to 1. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
| sold\_items | optional | Determines whether to filter Ebay search results to just 'sold items'. Valid values are true or false (default). |
| completed\_items | optional | Determines whether to filter Ebay search results to just 'completed items'. Valid values are true or false (default). |
| authorized\_sellers | optional | Determines whether to filter Ebay search results to just items offered by 'authorized sellers'. Valid values are true or false (default). |
| returns\_accepted | optional | Determines whether to filter Ebay search results to just 'returns accepted items'. Valid values are true or false (default). |
| free\_returns | optional | Determines whether to filter Ebay search results to just 'free returns items'. Valid values are true or false (default). |
| authenticity\_verified | optional | Determines whether to filter Ebay search results to just 'authenticity verified items'. Valid values are true or false (default). |
| deals\_and\_savings | optional | Determines whether to filter Ebay search results to just 'deals and savings items'. Valid values are true or false (default). |
| sale\_items | optional | Determines whether to filter Ebay search results to just 'sale items'. Valid values are true or false (default). |
| page | optional | Determines the page of results to return, defaults to 1. Use in combination with the num parameter to implement pagination. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
Next Steps

* [Ebay Search Results](/docs/search-api/results/ebay/search)

Baidu Search Parameters
-----------------------

GET`/search?engine=baidu`The Baidu Search Parameters are applicable when making a request with `engine=baidu` to retrieve Baidu search results for a given search term. The search term is specified in the `q` parameter.

![](https://apiimages.imgix.net/serpwow/images/png/docs/baidu_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Baidu Search ResultsFor example, to request Baidu search results for the keyword `pizza`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&engine=baidu&q=pizza
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d engine="baidu" \
-d q="pizza"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  engine: "baidu",
  q: "pizza"
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
  'engine': 'baidu',
  'q': 'pizza'
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
  'engine' => 'baidu',
  'q' => 'pizza'
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

Copy### Baidu Search Parameters

The following parameters are available for all requests made when `engine=baidu`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=baidu. |
| q | required | The keyword you want to use to perform the search. |
| query\_type | optional | Determines where Baidu searches for your query, can be set to page\_title (to have Baidu search within the page title - similar to Google's intitle: query parameter) or web\_address (to have Baidu search within the sites web address - similar to Google's inurl: query parameter). |
| results\_language | optional | Determines whether Baidu limits the results to those in specific languages, can be set to all (to remove any limit), simplified\_chinese or traditional\_chinese. |
| page | optional | Determines the page of results to return, defaults to 1. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
Next Steps

* [Baidu Search Results](/docs/search-api/results/baidu/search)

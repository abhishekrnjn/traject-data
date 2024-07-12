Yahoo Search Parameters
-----------------------

GET`/search?engine=yahoo`The Yahoo Search Parameters are applicable when making a request with `engine=yahoo` to retrieve Yahoo search results for a given search term. The search term is specified in the `q` parameter.

![](https://apiimages.imgix.net/serpwow/images/png/docs/yahoo_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Yahoo Search ResultsFor example, to request Yahoo search results for the keyword `pizza`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&engine=yahoo&q=pizza
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d engine="yahoo" \
-d q="pizza"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  engine: "yahoo",
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
  'engine': 'yahoo',
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
  'engine' => 'yahoo',
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

Copy### Yahoo Search Parameters

The following parameters are available for all requests made when `engine=yahoo`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=yahoo. |
| q | required | The keyword you want to use to perform the search. |
| country\_code | optional | The country\_code parameter determines the country to show results from. View the full list of supported Yahoo country\_code values view the Yahoo Country Codes reference. |
| page | optional | Determines the page of results to return, defaults to 1. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
Next Steps

* [Yahoo Search Results](/docs/search-api/results/yahoo/search)

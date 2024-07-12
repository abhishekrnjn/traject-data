Naver News Parameters
---------------------

GET`/search?engine=naver&search_type=news`The Naver News Parameters are applicable when making a request with `engine=naver` and `search_type=news` to retrieve Naver News results for a given search term. The search term is specified in the `q` parameter.

![](https://apiimages.imgix.net/serpwow/images/png/docs/naver_news.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Naver News ResultsFor example, to request Naver News results for the keyword `pizza`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&engine=naver&q=pizza
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d engine="naver" \
-d q="pizza"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  engine: "naver",
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
  'engine': 'naver',
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
  'engine' => 'naver',
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

Copy### Naver News Parameters

The following parameters are available for all requests made when `engine=naver` and `search_type=news`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=naver. |
| search\_type | required | Should be set to search\_type=news. |
| q | required | The keyword you want to use to perform the search. |
| page | optional | Determines the page of results to return, defaults to 1. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
Next Steps

* [Naver News Results](/docs/search-api/results/naver/news)

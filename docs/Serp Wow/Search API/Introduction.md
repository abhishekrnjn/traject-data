Overview
--------

SerpWow executes search requests in real time returning clean, structured`JSON``HTML`or`CSV`results. You can achieve fine-grained control over your search query using the [search parameters](/docs/search-api/searches/common).

With SerpWow you can run search queries against [Google](/docs/search-api/searches/google/search), [Bing](/docs/search-api/searches/bing/search), [Yahoo](/docs/search-api/searches/yahoo/search), [Baidu](/docs/search-api/searches/baidu/search), [Yandex](/docs/search-api/searches/yandex/search), [Naver](/docs/search-api/searches/naver/search), [Amazon](/docs/search-api/searches/amazon/search) or [Ebay](/docs/search-api/searches/ebay/search).

### Making a Request

GET`/search`Performing a search is as simple as making a `GET` HTTP request to the SerpWow `search` endpoint. The only required parameters are `api_key` ([sign up](https://app.serpwow.com/signup) for free to get an API key) and `q` (your search query).

For example, to search for the phrase `pizza` the SerpWow search request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&q=pizza
```

```
$ curl --get https://api.serpwow.com/live/search \
  -d api_key="demo" \
  -d q="pizza"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza"
}

// make the http GET request to SerpWow
axios.get('https://api.serpwow.com/live/search', { params })
  .then(response => {

    // print the JSON response from SerpWow
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
  'q': 'pizza'
}

# make the http GET request to SerpWow
api_result = requests.get('https://api.serpwow.com/live/search', params)

# print the JSON response from SerpWow
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'pizza'
]);

# make the http GET request to SerpWow
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

# print the JSON response from SerpWow
echo $api_result;
```
  
:::::

Copy[Open in Tab](https://api.serpwow.com/live/search?api_key=demo&q=pizza)  
:::hint



To view SerpWow JSON results clearly in your browser we recommend these extensions for [Chrome](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc) and [Firefox](https://addons.mozilla.org/en-GB/firefox/addon/jsonview/)  
:::

Lets say we want to refine our query to search for `pizza` within `London, UK`. Here's how we could use the SerpWow `location` parameter to achieve just that:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&q=pizza&location=London,England,United Kingdom
```

```
$ curl --get https://api.serpwow.com/live/search \
  -d api_key="demo" \
  -d q="pizza" \
  -d location="London,England,United Kingdom"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  location: "London,England,United Kingdom"
}

// make the http GET request to SerpWow
axios.get('https://api.serpwow.com/live/search', { params })
  .then(response => {

    // print the JSON response from SerpWow
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
  'q': 'pizza',
  'location': 'London,England,United Kingdom'
}

# make the http GET request to SerpWow
api_result = requests.get('https://api.serpwow.com/live/search', params)

# print the JSON response from SerpWow
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'pizza',
  'location' => 'London,England,United Kingdom'
]);

# make the http GET request to SerpWow
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

# print the JSON response from SerpWow
echo $api_result;
```
  
:::::

Copy[Open in Tab](https://api.serpwow.com/live/search?api_key=demo&q=pizza&location=London,England,United Kingdom)Now lets try the same search but in `Paris, France`. When we update the `location` parameter note how SerpWow automatically changes the `google_domain` parameter to`google.fr`and the `gl` (country) and `hl` (language) parameters to `hl=fr` (so you see localized results exactly as a human user in Paris would):



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&q=pizza&location=Paris,Ile-de-France,France
```

```
$ curl --get https://api.serpwow.com/live/search \
  -d api_key="demo" \
  -d q="pizza" \
  -d location="Paris,Ile-de-France,France"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  location: "Paris,Ile-de-France,France"
}

// make the http GET request to SerpWow
axios.get('https://api.serpwow.com/live/search', { params })
  .then(response => {

    // print the JSON response from SerpWow
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
  'q': 'pizza',
  'location': 'Paris,Ile-de-France,France'
}

# make the http GET request to SerpWow
api_result = requests.get('https://api.serpwow.com/live/search', params)

# print the JSON response from SerpWow
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'pizza',
  'location' => 'Paris,Ile-de-France,France'
]);

# make the http GET request to SerpWow
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

# print the JSON response from SerpWow
echo $api_result;
```
  
:::::

Copy[Open in Tab](https://api.serpwow.com/live/search?api_key=demo&q=pizza&location=Paris,Ile-de-France,France)Now lets take a look at how to paginate through results using the `page` and `num` parameters.`page`determines the page number of the results (starting from 1) and `num` determines the number of results to show per page. If we wanted to show the 2nd page of results, based on 10 results per page, our query would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&q=pizza&page=2&num=10
```

```
$ curl --get https://api.serpwow.com/live/search \
  -d api_key="demo" \
  -d q="pizza" \
  -d page="2" \
  -d num="10"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "pizza",
  page: "2",
  num: "10"
}

// make the http GET request to SerpWow
axios.get('https://api.serpwow.com/live/search', { params })
  .then(response => {

    // print the JSON response from SerpWow
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
  'q': 'pizza',
  'page': '2',
  'num': '10'
}

# make the http GET request to SerpWow
api_result = requests.get('https://api.serpwow.com/live/search', params)

# print the JSON response from SerpWow
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'pizza',
  'page' => '2',
  'num' => '10'
]);

# make the http GET request to SerpWow
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

# print the JSON response from SerpWow
echo $api_result;
```
  
:::::

Copy[Open in Tab](https://api.serpwow.com/live/search?api_key=demo&q=pizza&page=2&num=10)Lastly, SerpWow supports more than just Google! You can use SerpWow to run searches against Bing, Yahoo, Baidu, Yandex, Naver or Amazon search engines. It's as simple as using the `engine` parameter - see below for searching using Bing:


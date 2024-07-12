Overview
--------

Scale SERP executes search requests in real time returning clean, structured`JSON``HTML`or`CSV`results. You can achieve fine-grained control over your search query using the [search parameters](/docs/search-api/searches/common).

### Making a Request

GET`/search`Performing a search is as simple as making a `GET` HTTP request to the Scale SERP `search` endpoint. The only required parameters are `api_key` ([sign up](https://app.scaleserp.com/signup) for free to get an API key) and `q` (your search query).

For example, to search for the phrase `pizza` the Scale SERP search request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&q=pizza
```

```
$ curl --get https://api.scaleserp.com/search \
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

// make the http GET request to Scale SERP
axios.get('https://api.scaleserp.com/search', { params })
  .then(response => {

    // print the JSON response from Scale SERP
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

# make the http GET request to Scale SERP
api_result = requests.get('https://api.scaleserp.com/search', params)

# print the JSON response from Scale SERP
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'pizza'
]);

# make the http GET request to Scale SERP
$ch = curl_init(sprintf('%s?%s', 'https://api.scaleserp.com/search', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$api_result = curl_exec($ch);
curl_close($ch);

# print the JSON response from Scale SERP
echo $api_result;
```
Copy[Open in Tab](https://api.scaleserp.com/search?api_key=demo&q=pizza)

To view Scale SERP JSON results clearly in your browser we recommend these extensions for [Chrome](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc) and [Firefox](https://addons.mozilla.org/en-GB/firefox/addon/jsonview/)Lets say we want to refine our query to search for `pizza` within `London, UK`. Here's how we could use the Scale SERP `location` parameter to achieve just that:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&q=pizza&location=London,England,United Kingdom
```

```
$ curl --get https://api.scaleserp.com/search \
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

// make the http GET request to Scale SERP
axios.get('https://api.scaleserp.com/search', { params })
  .then(response => {

    // print the JSON response from Scale SERP
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

# make the http GET request to Scale SERP
api_result = requests.get('https://api.scaleserp.com/search', params)

# print the JSON response from Scale SERP
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'pizza',
  'location' => 'London,England,United Kingdom'
]);

# make the http GET request to Scale SERP
$ch = curl_init(sprintf('%s?%s', 'https://api.scaleserp.com/search', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$api_result = curl_exec($ch);
curl_close($ch);

# print the JSON response from Scale SERP
echo $api_result;
```
Copy[Open in Tab](https://api.scaleserp.com/search?api_key=demo&q=pizza&location=London,England,United Kingdom)Now lets try the same search but in `Paris, France`. When we update the `location` parameter note how Scale SERP automatically changes the `google_domain` parameter to`google.fr`and the `gl` (country) and `hl` (language) parameters to `hl=fr` (so you see localized results exactly as a human user in Paris would):



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&q=pizza&location=Paris,Ile-de-France,France
```

```
$ curl --get https://api.scaleserp.com/search \
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

// make the http GET request to Scale SERP
axios.get('https://api.scaleserp.com/search', { params })
  .then(response => {

    // print the JSON response from Scale SERP
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

# make the http GET request to Scale SERP
api_result = requests.get('https://api.scaleserp.com/search', params)

# print the JSON response from Scale SERP
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'pizza',
  'location' => 'Paris,Ile-de-France,France'
]);

# make the http GET request to Scale SERP
$ch = curl_init(sprintf('%s?%s', 'https://api.scaleserp.com/search', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$api_result = curl_exec($ch);
curl_close($ch);

# print the JSON response from Scale SERP
echo $api_result;
```
Copy[Open in Tab](https://api.scaleserp.com/search?api_key=demo&q=pizza&location=Paris,Ile-de-France,France)Now lets take a look at how to paginate through results using the `page` and `num` parameters.`page`determines the page number of the results (starting from 1) and `num` determines the number of results to show per page. If we wanted to show the 2nd page of results, based on 10 results per page, our query would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP
```
https://api.scaleserp.com/search?api_key=demo&q=pizza&page=2&num=10
```

```
$ curl --get https://api.scaleserp.com/search \
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

// make the http GET request to Scale SERP
axios.get('https://api.scaleserp.com/search', { params })
  .then(response => {

    // print the JSON response from Scale SERP
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

# make the http GET request to Scale SERP
api_result = requests.get('https://api.scaleserp.com/search', params)

# print the JSON response from Scale SERP
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

# make the http GET request to Scale SERP
$ch = curl_init(sprintf('%s?%s', 'https://api.scaleserp.com/search', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);

$api_result = curl_exec($ch);
curl_close($ch);

# print the JSON response from Scale SERP
echo $api_result;
```
Copy[Open in Tab](https://api.scaleserp.com/search?api_key=demo&q=pizza&page=2&num=10)
Locations API Overview
----------------------

GET`/locations`The SerpWow Locations API allows you to search for SerpWow supported Google & Bing search locations. You can supply the`full_name`returned by the Locations API as the`location`parameter in a [Search API](/docs/search-api) query to retrieve search results localized to that location.

  
:::hint



**The Locations API is Free of Charge**  
There is no charge for usage of the Locations API and requests to it will not decrement your monthly search credits. However, to guarantee quality of service to all customers, we do apply a rate limit of 120 requests per minute.  
:::

To search for the location`london`the SerpWow Locations API request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/locations?api_key=demo&q=london
```

```
$ curl --get https://api.serpwow.com/live/locations \
  -d api_key="demo" \
  -d q="london"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "london"
}

// make the http GET request to SerpWow
axios.get('https://api.serpwow.com/live/locations', { params })
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
  'q': 'london'
}

# make the http GET request to SerpWow
api_result = requests.get('https://api.serpwow.com/live/locations', params)

# print the JSON response from SerpWow
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'london'
]);

# make the http GET request to SerpWow
$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/locations', $queryString));
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

CopyHere are the results from the request above, note that the`locations`array contains the SerpWow supported locations matching the query supplied in the`q`parameter.


```
{
  "request_info": {
    "success": true
  },
  "locations": [
    {
      "id": 9041106,
      "name": "Greater London",
      "type": "County",
      "full_name": "Greater London,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 20800000
    },
    {
      "id": 1006886,
      "name": "London",
      "type": "City",
      "full_name": "London,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 19900000
    },
    {
      "id": 9041110,
      "name": "City of London",
      "type": "County",
      "full_name": "City of London,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 19900000
    },
    {
      "id": 1002316,
      "name": "London Borough of Lambeth",
      "type": "Municipality",
      "full_name": "London Borough of Lambeth,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 983000
    },
    {
      "id": 9057243,
      "name": "New London County",
      "type": "County",
      "full_name": "New London County,Connecticut,United States",
      "parent_id": 21139,
      "country_code": "US",
      "reach": 434000
    },
    {
      "id": 1002325,
      "name": "London",
      "type": "City",
      "full_name": "London,Ontario,Canada",
      "parent_id": 20121,
      "country_code": "CA",
      "reach": 418000
    },
    {
      "id": 1007284,
      "name": "Londonderry",
      "type": "City",
      "full_name": "Londonderry,Northern Ireland,United Kingdom",
      "parent_id": 20341,
      "country_code": "GB",
      "reach": 192000
    },
    {
      "id": 9041230,
      "name": "London Stansted Airport",
      "type": "Airport",
      "full_name": "London Stansted Airport,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 153000
    },
    {
      "id": 1017821,
      "name": "London",
      "type": "City",
      "full_name": "London,Kentucky,United States",
      "parent_id": 21150,
      "country_code": "US",
      "reach": 144000
    },
    {
      "id": 1014779,
      "name": "New London",
      "type": "City",
      "full_name": "New London,Connecticut,United States",
      "parent_id": 21139,
      "country_code": "US",
      "reach": 136000
    }
  ]
}
```
CopyLets say we want to refine our location query to search for locations matching`london`that are cities within Great Britain. To do that we use the`type`and`country_code`parameters:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/locations?api_key=demo&q=london&type=city&country_code=gb
```

```
$ curl --get https://api.serpwow.com/live/locations \
  -d api_key="demo" \
  -d q="london" \
  -d type="city" \
  -d country_code="gb"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "london",
  type: "city",
  country_code: "gb"
}

// make the http GET request to SerpWow
axios.get('https://api.serpwow.com/live/locations', { params })
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
  'q': 'london',
  'type': 'city',
  'country_code': 'gb'
}

# make the http GET request to SerpWow
api_result = requests.get('https://api.serpwow.com/live/locations', params)

# print the JSON response from SerpWow
print(json.dumps(api_result.json()))
```

```
# set up the request parameters
$queryString = http_build_query([
  'api_key' => 'demo',
  'q' => 'london',
  'type' => 'city',
  'country_code' => 'gb'
]);

# make the http GET request to SerpWow
$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/locations', $queryString));
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

CopyNote that the results now reflect just cities within the GB country code.


```
{
  "request_info": {
    "success": true
  },
  "locations": [
    {
      "id": 1006886,
      "name": "London",
      "type": "City",
      "full_name": "London,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 19900000
    },
    {
      "id": 1007284,
      "name": "Londonderry",
      "type": "City",
      "full_name": "Londonderry,Northern Ireland,United Kingdom",
      "parent_id": 20341,
      "country_code": "GB",
      "reach": 192000
    },
    {
      "id": 1006887,
      "name": "London Colney",
      "type": "City",
      "full_name": "London Colney,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 113000
    }
  ]
}
```
Copy### Running a Search Specifying a Location

You can pass the fully qualified (`full_name`) Location name into the`location`parameter of a Search API request to retrieve search results from that location. In the example below we are passing the Location of`Greater London,England,United Kingdom`, as retrieved from the`full_name`property in the Locations API response, in the Search API`location`parameter:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&q=coffee&location=Greater London,England,United Kingdom
```

```
$ curl --get https://api.serpwow.com/live/search \
  -d api_key="demo" \
  -d q="coffee" \
  -d location="Greater London,England,United Kingdom"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "coffee",
  location: "Greater London,England,United Kingdom"
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
  'q': 'coffee',
  'location': 'Greater London,England,United Kingdom'
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
  'q' => 'coffee',
  'location' => 'Greater London,England,United Kingdom'
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

Copy
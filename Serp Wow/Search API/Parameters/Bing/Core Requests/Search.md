Bing Search Parameters
----------------------

GET`/search?engine=bing`The Bing Search Parameters are applicable when making a request with `engine=bing` to retrieve Bing search results for a given search term. The search term is specified in the `q` parameter.

  
:::hint



**Setting Location for Bing requests**  
The recommended way of setting the location of your Bing request is to use the `location` parameter. The `location` parameter can be populated with a `full_name` value returned by the [Locations API](/docs/locations-api).  
  
You may also use either the `market_code` or `country_code` parameters to set the location of your request, but the recommended approach is to use the `location` parameter as this sets all the required prerequisites to achieve a correctly geo-located result.  
:::

![](https://apiimages.imgix.net/serpwow/images/png/docs/bing_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Bing Search ResultsFor example, to request Bing search results for the keyword `pizza`, in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&engine=bing&q=pizza+United+States
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d engine="bing" \
-d location="United States" \
-d q="pizza"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  engine: "bing",
  location: "United States",
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
  'engine': 'bing',
  'location': 'United States',
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
  'engine' => 'bing',
  'location' => 'United States',
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

Copy### Bing Search Parameters

The following parameters are available for all search requests made when `engine=bing`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=bing. |
| q | required | The keyword you want to use to perform the search. |
| location | optional | Determines the geographic location in which the query is executed. You must enter a full\_name value from the SerpWow Locations API, for example location=Richmond+County,New+York,United+States (where Richmond+County,New+York,United+States is the full\_name as-returned by the Locations API).Note the location parameter is the recommended way of setting the location of your Bing request. |
| market\_code | optional | The market\_code parameter determines the Bing-defined market to show results from. This is typically the country in which the user is making requests.View the full list of supported Bing market\_code values here.Note the market\_code parameter cannot be used in combination with the country\_code parameter. |
| country\_code | optional | The country\_code parameter determines the country to show results from (if market\_code is not specified).View the full list of supported Bing country\_code values here.Note it is recommended that the market\_code parameter be used instead of country\_code. The country\_code parameter cannot be used in combination with the market\_code parameter. |
| bing\_language | optional | The bing\_language parameter determines the Bing UI language to return results. View the full list of supported bing\_languagevalues here. Defaults to en. |
| page | optional | Determines the page of results to return, defaults to 1. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
| num | optional | Determines the number of results to show per page. Use in combination with the page parameter to implement pagination.Note num must be set to 50 or less (this is a Bing-imposed limitation of not returning more than 50 results per page). |
| include\_answer\_box | optional | Determines whether to include the answer box (sometimes called the "featured snippet") in the organic\_results array and treat it as the first result. This may be desirable if you treat the result Bing displayed in the answer\_box as the first organic result. |
| safe | optional | Determines whether Safe Searchis enabled for the results. Can be set to strict to enable Safe Search, moderate for just images and videos or off to disable Safe Search. |
Next Steps

* [Bing Search Results](/docs/search-api/results/bing/search)

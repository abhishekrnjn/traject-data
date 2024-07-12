Yandex Search Parameters
------------------------

GET`/search?engine=yandex`The Yandex Search Parameters are applicable when making a request with `engine=yandex` to retrieve Yandex search results for a given search term. The search term is specified in the `q` parameter and the optional `yandex_domain` parameter can be used to specify the Yandex domain used for the request. Supported Yandex domains are `yandex.com` and `yandex.ru`.

  
:::hint



**Setting the location of Yandex requests**  
The `yandex_location` parameter can be used to localize your Yandex request. The `yandex_location` parameter is only available on the `yandex.ru` domain - i.e. when your request has the `yandex_domain=yandex.ru` request parameter set.  
  
View the full list of supported `yandex_location` values [here](/docs/search-api/reference/yandex-locations)  
:::

![](https://apiimages.imgix.net/serpwow/images/png/docs/yandex_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Yandex Search ResultsFor example, to request Yandex search results for the keyword `pizza` on `yandex.com`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&engine=yandex&yandex_domain=yandex.com&q=pizza
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d engine="yandex" \
-d yandex_domain="yandex.com" \
-d q="pizza"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  engine: "yandex",
  yandex_domain: "yandex.com",
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
  'engine': 'yandex',
  'yandex_domain': 'yandex.com',
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
  'engine' => 'yandex',
  'yandex_domain' => 'yandex.com',
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

Copy### Yandex Search Parameters

The following parameters are available for all requests made when `engine=yandex`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=yandex. |
| q | required | The keyword you want to use to perform the search. |
| yandex\_domain | optional | The Yandex domain to retrieve search results from. Supported Yandex domains are yandex.com and yandex.ru. Defaults to yandex.com. |
| yandex\_location | optional | The yandex\_location parameter determines the Yandex-defined location to show results from. This is typically the country or location in which the user is making requests. For example yandex\_location=177 for Berlin, Germany.View the full list of supported yandex\_location values here.Note the yandex\_location parameter only functions when yandex\_domain=yandex.ru. It cannot be used with any other yandex\_domain. |
| yandex\_language | optional | The yandex\_language parameter determines the Yandex UI language to return results. View the full list of supported yandex\_languagevalues here. |
| page | optional | Determines the page of results to return, defaults to 1. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
Next Steps

* [Yandex Search Results](/docs/search-api/results/yandex/search)

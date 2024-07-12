Google Reverse Image Parameters
-------------------------------

GET`/search?engine=google&search_type=reverse_image_search`SerpWow parses the Google Reverse Image search results the `visual_matches` property in the JSON output when the `search_type=reverse_image_search` search parameter is set.

The image to perform the reverse image search on is supplied in the `image_url` request parameter.

  
:::hint



**Specifying an `image_url`**  
You must supply a publicly Internet-accessible image URL in the `image_url` parameter. The `image_url` cannot be a private internal URL - it must be publicly accessible.  
**Important** your `image_url` must be URL-encoded.  
:::

![]()Google Reverse Image ResultsFor example, to request reverse image results for the `image_url` of `<https://assets.api-cdn.com/serpwow/apple.jpg>`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=reverse_image_search&image_url=https%3A%2F%2Fassets.api-cdn.com%2Fserpwow%2Fapple.jpg
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d image_url="https://assets.api-cdn.com/serpwow/apple.jpg" \
-d search_type="reverse_image_search"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  image_url: "https://assets.api-cdn.com/serpwow/apple.jpg",
  search_type: "reverse_image_search"
}

// make the http GET request
axios.get('https://api.serpwow.com/live"/search', { params })
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
  'image_url': 'https://assets.api-cdn.com/serpwow/apple.jpg',
  'search_type': 'reverse_image_search'
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
  'image_url' => 'https://assets.api-cdn.com/serpwow/apple.jpg',
  'search_type' => 'reverse_image_search'
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

Copy### Google Reverse Image Parameters

The following parameters are available for all requests made when `search_type=reverse_image_search`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=reverse\_image\_search. |
| image\_url | required | The publicly-accessible image URL to use for the Reverse Image search. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
Next Steps

* [Google Reverse Image Results](/docs/search-api/results/google/reverse-image)

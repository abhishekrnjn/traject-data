Google Scholar Parameters
-------------------------

GET`/search?engine=google&search_type=scholar`The Google Scholar Parameters are applicable when making a request with `search_type=scholar` to retrieve scholar results for a given search term. The search term is specified in the `q` parameter and the optional `location` parameter can be used to geo-locate the scholar request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_scholar.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Scholar ResultsFor example, to request scholar results for the keyword `rubifen` in the location `United States`, the request would be:



HTTP



image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
https://api.serpwow.com/live/search?api_key=demo&search_type=scholar&q=rubifen&location=United+States
```

```
curl -L --get https://api.serpwow.com/live/search \
-d api_key="demo" \
-d q="rubifen" \
-d search_type="scholar" \
-d location="United+States"
```

```
const axios = require('axios');

// set up the request parameters
const params = {
  api_key: "demo",
  q: "rubifen",
  search_type: "scholar",
  location: "United+States"
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
  'q': 'rubifen',
  'search_type': 'scholar',
  'location': 'United+States'
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
  'q' => 'rubifen',
  'search_type' => 'scholar',
  'location' => 'United+States'
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

Copy### Google Scholar Parameters

The following parameters are available for all requests made when `search_type=scholar`.

| Parameter | Required | Description |
| --- | --- | --- |
| engine | required | Should be set to engine=google. |
| search\_type | required | Should be set to search\_type=scholar. |
| q | required | The keyword you want to use to perform the Scholar search. |
| location | optional | Determines the geographic location in which the query is executed. You can enter any location as free-text, but if you choose one of the SerpWow built-in locations then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location (note that this behaviour can be disabled via the location\_autoparameter). |
| location\_auto | optional | If the locationfield is set to a SerpWow built-in location from the Locations API, and location\_autois set to true (default) then the google\_domain, gland hlparameters are automatically updated to the domain, country and language that match the built-in location. Valid values are true (default) to enable this behaviour or falseto disable. |
| uule | optional | The Google UULE parameter - use to pass through a custom uule parameter to Google. SerpWow automatically generates the uule when you use the location parameter but we allow you to overwrite it directly by specifying a uule directly. |
| google\_domain | optional | The Google domain to use to run the search query. View the full list of supported google\_domainvalues here. Defaults to google.com. |
| gl | optional | The gl parameter determines the Google country to use for the query. View the full list of supported glvalues here. Defaults to us. |
| hl | optional | The hl parameter determines the Google UI language to return results. View the full list of supported hlvalues here. Defaults to en. |
| lr | optional | The lr parameter limits the results to websites containing the specified language. View the full list of supported lrvalues here. |
| cr | optional | The cr parameter instructs Google to limit the results to websites in the specified country. View the full list of supported crvalues here. |
| page | optional | Determines the page of results to return, defaults to 1. |
| max\_page | optional | Use the max\_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.See the Pagination docs for more information. |
| sort\_by | optional | Determines how results are sorted, valid values are relevance or date. |
| scholar\_include\_citations | optional | Determines whether to include citations or not when the search\_typeparameter is set to scholar. Valid values are trueor false. Defaults to true. Drives the following option: |
| scholar\_year\_min | optional | Determines the year from which results should be included when search\_type=scholar. For example, if you set scholar\_year\_min=2018 the results before 2018 will be omitted. This parameter can be combined with the scholar\_year\_max parameter. |
| scholar\_year\_max | optional | Determines the year from which results should be included when search\_type=scholar. For example, if you set scholar\_year\_max=2019 the results after 2019 will be omitted. This parameter can be combined with the scholar\_year\_min parameter. |
| scholar\_patents\_courts | optional | The scholar\_patents\_courts parameter can be used either as both a way of limiting the Scholar search or as a filter (this is due to how Google implements this parameter itself).As a Filter the valid values are:0 (default) - include patents1 - exclude patentsAs a way of limiting a Scholar search the valid values are:4 - case law (US courts only). This will select all the State and Federal courts.To select specific courts, see the full list of supported Google Scholar courts.For example, scholar\_patents\_courts=4,33,192 4 is the required value and should always be in the first position, 33 selects all New York courts and 192 selects Tax Court. Values must be separated by a comma. |
| scisbd | optional | The Scholar scisbd parameter can be set to 1 or 2. |
Next Steps

* [Google Scholar Results](/docs/search-api/results/google/scholar)

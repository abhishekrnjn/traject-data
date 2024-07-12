Delete Destination
------------------

Destinations can be deleted by making an`HTTP DELETE`request to the`/destinations/DESTINATION_ID`endpoint (where`DESTINATION_ID`is the`id`of the Destination you wish to delete).

### Example

DELETE`/destinations/DESTINATION_ID`In the example below we delete a Destination with`id=ABCDEFG`:





image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
$ curl -X DELETE "https://api.serpwow.com/live/destinations/ABCDEFG?api_key=demo"
```

```
const axios = require('axios');
const params = {
  api_key: 'demo'
}

axios.delete('https://api.serpwow.com/live/destinations/ABCDEFG', { params })
  .then(response => {

    console.log('Destination deleted.');

  }).catch(error => {
    console.log(error);
  });
```

```
import requests
import json

api_result = requests.delete('https://api.serpwow.com/live/destinations/ABCDEFG?api_key=demo')

print ("Destination deleted.")
```

```
<?php
      
$queryString = http_build_query([
  'api_key' => 'demo',
]);

$ch = curl_init(sprintf('%s?%s', 'https://api.serpwow.com/live/destinations/ABCDEFG', $queryString));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "DELETE");

$json = curl_exec($ch);
curl_close($ch);

echo "Destination deleted.", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with a JSON object confirming that the Destination has been deleted, or detailing the error if it has not been possible to delete the Destination:


```
{
  "request_info": {
    "success": true,
    "message": "1 Destination deleted"
  }
}
```
CopyNext Steps

* [List Destinations](/docs/destinations-api/list)
* [Update Destination](/docs/destinations-api/update)

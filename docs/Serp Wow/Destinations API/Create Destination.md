Create Destination
------------------

Create a Destination to upload Batch Result Sets to on completion.

Destinations are created by making an `HTTP POST` to the `/destinations` endpoint. POST parameters can be either supplied as `x-www-form-urlencoded` parameters or by POST'ing a`JSON` object.

### Example

POST`/destination`To create a new Amazon S3 Destination the request would be as shown below:

  
:::hint



**Verifying your Destination**  
Whenever you create a new `enabled` Destination, or enable a previous disabled Destination, or update an existing Destination's credentials, SerpWow will upload and then delete a small test file to the Destination to verify connectivity. If this connectivity test fails then the create/update operation itself fails.  
:::





image/svg+xml
































CurlNode.JSPythonPHP  
:::::codeblocktabs


```
$ curl "https://api.serpwow.com/live/destinations?api_key=demo" \
  -d name="My First S3 Destination" \
  -d type="s3" \
  -d enabled=true \
  -d s3_access_key_id="my_access_key_id" \
  -d s3_secret_access_key="my_secret_access_key" \
  -d s3_bucket_name="MyS3Bucket" \
  -d s3_path_prefix="my_path_prefix"
```

```
const axios = require('axios');
const body = {
  name: 'My First S3 Destination',
  type: "s3",
  enabled: true,
  s3_access_key_id: 'my_access_key_id',
  s3_secret_access_key: 'my_secret_access_key',
  s3_bucket_name: 'MyS3Bucket',
  s3_path_prefix: 'my_path_prefix'
}

axios.post('https://api.serpwow.com/live/destinations?api_key=demo', body)
  .then(response => {
    const apiResponse = response.data;

    console.log('Destination Created: ' + JSON.stringify(apiResponse, 0, 2));

  }).catch(error => {
    console.log(error);
  });
```

```
import requests
import json

body = {
  "name": "My First S3 Destination",
  "type": "s3",
  "enabled": True,
  "s3_access_key_id": "my_access_key_id",
  "s3_secret_access_key": "my_secret_access_key",
  "s3_bucket_name": "s3_bucket_name",
  "s3_path_prefix": "my_path_prefix"
}

api_result = requests.post('https://api.serpwow.com/live/destinations?api_key=demo', json=body)

api_response = api_result.json()

print("Destination Created: " + json.dumps(api_response))
```

```
<?php

$body = http_build_query([
  "name" => "My First S3 Destination",
  "type" => "s3",
  "enabled" => false,
  "s3_access_key_id" => "my_access_key_id",
  "s3_secret_access_key" => "my_secret_access_key",
  "s3_bucket_name" => "s3_bucket_name",
  "s3_path_prefix" => "my_path_prefix"
]);

$ch = curl_init('https://api.serpwow.com/live/destinations?api_key=demo');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
# the following options are required if you're using an outdated OpenSSL version
# more details: https://www.openssl.org/blog/blog/2021/09/13/LetsEncryptRootCertExpire/
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_TIMEOUT, 180);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "POST");
curl_setopt($ch, CURLOPT_POSTFIELDS, $body);

$json = curl_exec($ch);
curl_close($ch);

$api_result = json_decode($json, true);

print_r($api_result);

echo "Destination Created", PHP_EOL;

?>
```
  
:::::

CopySerpWow responds with the following JSON confirming the Destination has been successfully created.


```
{
  "request_info": {
    "success": true
  },
  "destination": {
    "id": "ABCDEFG"
  }
}
```
Copy### Destination Parameters

POST`/destinations`The following parameters can be used when creating a Destination. The `api_key` parameter should be supplied as a querystring parameter on the request URL.

Parameters pther than `api_key` should be supplied in either `x-www-form-urlencoded` or `JSON` format, in the request body.

| Parameter | Required | Description |
| --- | --- | --- |
| api\_key | required | The API key for your account, should be supplied on the request querystring, i.e. api\_key=demo |
| name | required | The name of the Destination. |
| enabled | required | Determines whether the Destination is enabled or not. Disabled Destinations do not have Batch Result Sets uploaded to them, even if the Destination is set of a Batch.Parameter ValuestrueDestination is enabledfalseDestination is disabled |
| type | required | Determines the type of Destination.Parameter Valuess3Specifies that this Destination is for an Amazon S3 bucket.gcsSpecifies that this Destination is for a Google Cloud Storage bucket.azureSpecifies that this Destination is for Microsoft Azure Blob Storage.ossSpecifies that this Destination is for a Alibaba Cloud OSS bucket.s3compatibleSpecifies that this Destination is an S3 compatible object storage provider.Note that when type=s3compatible an S3-compatible endpoint must be supplied in the s3\_endpoint parameter. |
| s3\_access\_key\_id | required | Applies only when type=s3 or type=s3compatibleThe Amazon S3 Access Key ID. We strongly recommend you set up credentials specifically for SerpWow to use. |
| s3\_secret\_access\_key | required | Applies only when type=s3 or type=s3compatibleThe Amazon S3 Secret Access Key. We strongly recommend you set up credentials specifically for SerpWow to use. |
| s3\_bucket\_name | required | Applies only when type=s3 or type=s3compatibleThe Amazon S3 bucket name to use. |
| s3\_path\_prefix | optional | Applies only when type=s3 or type=s3compatibleThe Amazon S3 path prefix to prepend to Batch Result Set files when they are uploaded to your bucket.The text tokens %BATCH\_ID%, %BATCH\_NAME%, %RESULT\_SET\_ID% and %DATE% will be replaced with the Batch ID, Batch name, Result Set ID and UTC date (in the form YYYY\_MM\_DD) respectively when the files are uploaded. |
| s3\_endpoint | required | Applies only when type=s3compatibleThe Endpoint to use when connecting to S3 compatible storage (i.e. when type=s3compatible) For example https://ams3.digitaloceanspaces.com |
| s3\_region | optional | Applies only when type=s3compatibleThe region to use when connecting to S3 compatible storage (i.e. when type=s3compatible) For example eu-west-1, us-east-1, auto, etc |
| gcs\_access\_key | required | Applies only when type=gcsThe interoperable storage access key to use when connecting to Google Cloud Storage. We strongly recommend you set up credentials specifically for SerpWow to use. |
| gcs\_secret\_key | required | Applies only when type=gcsThe interoperable storage secret key used when connecting to Google Cloud Storage. We strongly recommend you set up credentials specifically for SerpWow to use. |
| gcs\_bucket\_name | required | Applies only when type=gcsThe Google Cloud Storage bucket name to use. |
| gcs\_path\_prefix | optional | Applies only when type=gcsThe Google Cloud Storage path prefix to prepend to Batch Result Set files when they are uploaded to your bucket.The text tokens %BATCH\_ID%, %BATCH\_NAME%, %RESULT\_SET\_ID% and %DATE% will be replaced with the Batch ID, Batch name, Result Set ID and UTC date (in the form YYYY\_MM\_DD) respectively when the files are uploaded. |
| azure\_account\_name | required | Applies only when type=azureThe storage account name to use when connecting to Microsoft Azure Blob Storage. We strongly recommend you set up credentials specifically for SerpWow to use. |
| azure\_account\_key | required | Applies only when type=azureThe account key used when connecting to Microsoft Azure Blob Storage. We strongly recommend you set up credentials specifically for SerpWow to use. |
| azure\_container\_name | required | Applies only when type=azureThe Microsoft Azure Blob Storage container name to use. |
| azure\_path\_prefix | optional | Applies only when type=azureThe Microsoft Azure Blob Storage path prefix to prepend to Batch Result Set files when they are uploaded to your bucket.The text tokens %BATCH\_ID%, %BATCH\_NAME%, %RESULT\_SET\_ID% and %DATE% will be replaced with the Batch ID, Batch name, Result Set ID and UTC date (in the form YYYY\_MM\_DD) respectively when the files are uploaded. |
| oss\_access\_key | required | Applies only when type=ossThe RAM user access key to use when connecting to Alibaba Cloud OSS. We highly recommend creating a new Alibaba Cloud RAM user specifically for SerpWow to use. You can do so in your Alibaba Cloud console |
| oss\_secret\_key | required | Applies only when type=ossThe RAM user secret key used when connecting to Alibaba Cloud OSS. We highly recommend creating new Alibaba Cloud RAM user specifically for SerpWow to use. You can do so in your Alibaba Cloud console |
| oss\_bucket\_name | required | Applies only when type=ossThe Alibaba Cloud OSS bucket name to use. |
| oss\_region\_id | required | Applies only when type=ossThe Alibaba Cloud OSS Region ID to use when connecting to your bucket.oss-cn-hangzhou - China (Hangzhou)oss-cn-shanghai - China (Shanghai)oss-cn-qingdao - China (Qingdao)oss-cn-beijing - China (Beijing)oss-cn-zhangjiakou - China (Zhangjiakou)oss-cn-huhehaote - China (Hohhot)oss-cn-wulanchabu - China (Ulanqab)oss-cn-shenzhen - China (Shenzhen)oss-cn-heyuan - China (Heyuan)oss-cn-guangzhou - China (Guangzhou)oss-cn-chengdu - China (Chengdu)oss-cn-hongkong - China (Hong Kong)oss-us-west-1 - US (Silicon Valley)oss-us-east-1 - US (Virginia)oss-ap-southeast-1 - Singaporeoss-ap-southeast-2 - Australia (Sydney)oss-ap-southeast-3 - Malaysia (Kuala Lumpur)oss-ap-southeast-5 - Indonesia (Jakarta)oss-ap-northeast-1 - Japan (Tokyo)oss-ap-south-1 - India (Mumbai)oss-eu-central-1 - Germany (Frankfurt)oss-eu-west-1 - UK (London)oss-me-east-1 - UAE (Dubai) |
| oss\_path\_prefix | optional | Applies only when type=ossThe Alibaba Cloud OSS path prefix to prepend to Batch Result Set files when they are uploaded to your bucket.The text tokens %BATCH\_ID%, %BATCH\_NAME%, %RESULT\_SET\_ID% and %DATE% will be replaced with the Batch ID, Batch name, Result Set ID and UTC date (in the form YYYY\_MM\_DD) respectively when the files are uploaded. |
Next Steps

* [List Destinations](/docs/destinations-api/list)
* [Update Destination](/docs/destinations-api/update)

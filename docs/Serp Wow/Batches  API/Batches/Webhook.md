Webhook
-------

When a Batch has its`notification_webhook`property set SerpWow will make an`HTTP POST`to this URL when the Batch completes and a new [Result Set](/docs/batches-api/results/list) is available.

  
:::hint



Note that if no Webhook URL is supplied in the Batch's`notification_webhook`property SerpWow will fallback to using the Webhook URL defined on your account [profile](https://app.serpwow.com/profile).  
:::

  
:::hint



Note that the webhook has a timeout of 5 seconds, your app should ingest the webhook HTTP POST within this timeout. If your app takes longer than 5 seconds to respond the API will terminate the HTTP POST.If a timeout does occur then we won't attempt to call the same webhook url for another 5 minutes, this applies to all Batches that are using the same webhook url.   
:::

The body of the Webhook`POST`contains details of the Batch along with download links for the Result Set. Note that the presence of the`json`and`csv`download links in the response JSON depends on whether the Batch has the `notification_as_json`, `notification_as_jsonlines` and `notification_as_csv`properties set.

Here's an example of the body of the Webhook `POST`:


```
{
  "request_info": {
    "success": true,
    "type": "batch_resultset_completed"
  },
  "batch": {
    "id": "9E867FAA",
    "name": "My Second Batch"
  },
  "result_set": {
    "id": 4,
    "started_at": "2020-01-01T00:00:00.000Z",
    "ended_at": "2020-01-01T00:00:10.000Z",
    "searches_completed": 1,
    "searches_failed": 0,
    "download_links": {
      "json": {
        "pages": [
          "https://results.serpwow.com/Batch_Results_9E867FAA_4_Page_1.json"
        ],
        "all_pages": "https://results.serpwow.com/Batch_Results_9E867FAA_4_All_Pages.zip"
      },
      "csv": {
        "pages": [
          "https://results.serpwow.com/Batch_Results_9E867FAA_4_Page_1_246f6e2e561c90958384aa76e455e2bc95ad3a01.csv"
        ],
        "all_pages": "https://results.serpwow.com/Batch_Results_9E867FAA_4_All_Pages_246f6e2e561c90958384aa76e455e2bc95ad3a01.csv"
      }
    }
  }
}
```
CopyNext Steps

* [List Searches](/docs/batches-api/searches/list)
* [List Result Sets](/docs/batches-api/results/list)
* [Resending a Webhook](/docs/batches-api/results/resend-webhook)

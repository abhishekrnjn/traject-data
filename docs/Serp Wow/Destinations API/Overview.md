Destinations API
----------------

Destinations allow you to automatically send Batch Result Sets to destinations you define. Supported destinations are Amazon S3, Google Cloud Storage, Microsoft Azure Blob Storage, Alibaba Cloud OSS or any other S3-compatible object storage.

Destinations are useful for when you want data obtained by running your SerpWow Batches to to automatically pushed to a storage provider you already use, rather than downloading the Results Sets directly from SerpWow.

  
:::hint



**Destination Limits & Security**  
You can have up to 50 Destinations set up on your SerpWow account at any one time. We highly recommend creating new credentials just for use by SerpWow on your destination provider.  
:::

You can create Destinations via the SerpWow [dashboard](https://app.serpwow.com/destinations), or programmatically via the Destinations API. You can set each Batch on your account to upload its Result Sets to one or more Destinations.

Next Steps

* [Create Destinations](/docs/destinations-api/create)
* [List Destinations](/docs/destinations-api/list)

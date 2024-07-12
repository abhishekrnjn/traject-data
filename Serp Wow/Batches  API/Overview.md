Batches API
-----------

Batches allow you to schedule Searches to run en masse. You can add up to 15,000 Searches (a Search is simply a call to the Search API) per Batch (100 per Batch if using the `include_html=true` request parameter) and you can have up to 10,000 Batches on your account at any one time.

Batches can be scheduled to run monthly, weekly, daily, hourly or run manually on-demand and you can get Result Sets in JSON, JSON Lines or CSV formats. SerpWow can also call a [webhook](/docs/batches-api/batches/webhook) on your side when Batches complete.

  
:::hint



**Batch & Result Set Expiry**  
Batches will be deleted from your account after 2 months of inactivity - i.e. you must [start](/docs/batches-api/batches/start) a Batch at least once every two months for it to remain active.  
  
Result Sets are available for download for 14 days so your app should download and process the Result Set data within this 14 day window.  
:::

The SerpWow Batches API allows you to [create](/docs/batches-api/batches/create), [update](/docs/batches-api/batches/update) and [delete](/docs/batches-api/batches/delete) Batches. You can also use the Batches API to add [Searches](/docs/batches-api/searches/create) to a Batch and retrieve [Result Sets](/docs/batches-api/results/list).

  
:::hint



**The Batches API is Free of Charge**  
There is no charge for usage of the Batches API and requests to it will not decrement your plans monthly searches quota. When you [start](/docs/batches-api/batches/start) a Batch the searches within the Batch will be charged as per requests made via the [Search API](/docs/search-api). So a Batch with 200 searches in it, run once, will cost 200 credits.  
:::

The SerpWow Dashboard also provides a [visual editor](https://app.serpwow.com/batches) for Batches and is a great way to get familiar with the key concepts in Batches before creating them programmatically through the Batches API.

### Batches Terminology

To help you get started here's some of the terminology you'll encounter whilst interacting with Batches on SerpWow:

#### Batch

You can have 10,000 Batches active on your account at any one time. A Batch holds (up to 15,000) Searches. A Batch can have a schedule and can be set to start automatically or manually. When a Batch is started, its Searches are run through the SerpWow Search API and a Result Set is generated. Batches can notify you when a new Result Set is available via email or webhook POST. **SerpWow will automatically delete Batches that have not been run for 2 months.**.

If you start multiple Batches they are queued and processed sequentially. To control the order of processing you can assign each Batch a `priority`. Higher priority Batches are started before lower priority ones. Learn more about [priorities](/docs/batches-api/priorities).

#### Search

A Batch can contain up to 15,000 Searches (100 when adding searches with `include_html=true`). A Search is simply a collection of parameters relating to an individual request to the Search API.

#### Result Set

When Batches complete (that is, when all of their Searches have been evaluated) a Result Set is generated. You can use the Batches API to retrieve Result Sets and ingest them into your app. **SerpWow retains Result Sets for 14 days so you should download your Result Set data within this 14 day window.**

SerpWow provides API's to retrieve Result Sets in JSON and CSV formats.

Next Steps

* [Create Batch](/docs/batches-api/batches/create)
* [Adding Searches to a Batch](/docs/batches-api/searches/create)
* [List Result Sets](/docs/batches-api/results/list)

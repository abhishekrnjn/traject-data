Product Updates
---------------

We're continuously updating Scale SERP to add features and functionality, most of which are a direct result of requests from customers. See the latest updates below. Within the [Scale SERP Dashboard](https://app.scaleserp.com/product-updates) you can subscribe to be alerted via email when new updates are released.

### April 2024

Update TypeDetailNew Feature#### Google Search: Discussions and Forums added to Scale SERP's search results

Google’s Discussions and Forums are now included in Scale SERP's search results. The Discussion and Forums object provides links to various forums and online discussions. For example, if you are searching "Planning a Disney vacation," Google will link you to discussions and forums to help you research the topic. The Scale SERP `discussions_and_forums` object returns the properties: `discussion_title`, `link`, `source` information and `block_position` in its results.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()### March 2024

Update TypeDetailNew Feature#### Questions and Answers are now included in Scale SERP's Google results

Google’s Questions & Answers is a SERP feature that lists the sources for closely related questions and answers based on the question asked in a search query. Scale SERP's `questions_and_answers` object returns the properties: `question`, `answer`, `votes` and `source` in its results.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()New Feature#### Google Search: Explore Brands results available

Scale SERP now returns the `explore_brands` object in Google search results (desktop and mobile). The Explore Brands object lists suggested brands based on the search query with product descriptions and links to the product. Properties included are: `title`, `description`, `link`, `image` and `description`.

  


Note: This feature is currently only available for `engine=google`.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()### July 2023

Update TypeDetail#### Meet Our Newest API! 🎉

We’ve just launched [Backyard API](https://www.backyardapi.com/), our real-time Lowe’s product data API and companion to BigBox API for **home improvement data**. Let us know what you think of our newest addition or 

if you need any help. As always, you can try it out free!

### June 2023

Update TypeDetailNew Feature#### Google Search: Shopping graph results available

Scale SERP can now return the shopping elements that appear in Search results (desktop and mobile) as `shopping_graphs`. This Google feature is currently available only for searches on google.com.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()Enhancement#### Ad\_carousel (sponsored) is now returned in Google Shopping search results

`Ad_carousel` is an array of Sponsored Shopping Result objects found within the carousel.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/shopping)![]()### April 2023

Update TypeDetail#### Business Update

As a result of significant growth, our infrastructure — namely the dynamic routing of traffic to accommodate high volume customers — has recently required updates. Reworking architecture patterns and proxy configurations has taken us a fair amount of time, which in turn has led to some slower customer issue resolution.

  


We'd like to assure you that we’ve identified and corrected the infrastructural shortcomings, and the outcome is a 50% increase in infrastructure and proxy capacity. We apologize for the potential business interruptions you may have experienced over the last couple months. Our aim is to earn your trust back and continue to support the realization of your business goals. Please don’t hesitate to get in touch if you require further information.

### Feburary 2023

Update TypeDetailEnhancement#### Geo-target by latitude and longitude for Google searches

Scale SERP can now target Google searches by latitude and longitude.

`Location:lat:37.32646,lon:-121.80163` 

  


Make sure to include the gl & hl parameters.



[Read More](https://www.scaleserp.com/docs/search-api/searches/google/search)### November 2022

Update TypeDetailEnhancement#### Live and Video result types added for Google Top Stories

Two new boolean properties video and live have been added to top\_stories results. True if a top story is video format, False if not. And True when a top story is a live video, False if not.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()### July 2022

Update TypeDetailEnhancement#### Search Tabs added to organic SERP results

A `search_tabs` array property has been added to the `search_information` object for organic SERP pages. This new property shows which search result types (i.e. Maps, Images, News etc) are available for the given query.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()Enhancement#### Scholarly Articles returned for organic web searches

A new field `scholarly_articles` has been added to the APIs organic web search results to expose the Scholarly Articles section (containing links to Google Scholar) at the top of the SERP.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()### June 2022

Update TypeDetailNew Feature#### Support for custom S3-compatible object stores in Destinations

It's now possible to specify a custom S3 endpoint to have Destinations upload Result Sets to any S3 compatible object store.



[Read More](https://www.scaleserp.com/docs/destinations-api/overview)![]()### May 2022

Update TypeDetailEnhancement#### Typical Prices from Across the Web parsed for Google Products

A new property for Google Product parsing has been added - `typical_prices_across_web`. The property shows the low and high price values, parsed with currency values.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/product)![]()### April 2022

Update TypeDetailEnhancement#### Enhanced Film Info parsing

A new `film_info` object has been added to the organic web search parsing to extract detailed information about film listings, including title, genre, reviews, VOD services etc.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()### Feburary 2022

Update TypeDetailNew Feature#### Inline Recipes returned in Google web results

A new `inline_recipes` property has been added to regular Google organic web search results to return the food recipe data shown inline with organic search results.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()Enhancement#### Enhanced "about this result" Google organic results parsing

The `about_this_result` parsing has been updated to extract the "search terms" and "related terms" sections of the result.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()### January 2022

Update TypeDetailNew Feature#### Nested Results added to organic results parsing

A new `nested_results` array, showing any results nested under an organic result, has been added to objects in the `organic_results` array for regular web search results.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/search)![]()### December 2021

Update TypeDetailEnhancement#### HTML review body added to Place Reviews results

The full HTML body of the review has been added to `search_type=place_reviews` responses to allow customized parsing of the HTML content.



[Read More](https://www.scaleserp.com/docs/search-api/results/google/place-reviews)![]()### November 2021

Update TypeDetailEnhancement#### Select all CSV Fields

We have added Select All / Select None options to quickly select all CSV fields in the Batch editor and API Playground to make choosing CSV fields much quicker.



[Read More](https://app.scaleserp.com)### September 2021

Update TypeDetailEnhancement#### "has\_product\_page" property added to Shopping results

A new boolean proper `has_product_page` has been added to `search_type=shopping` results. When `has_product_page=true` you may use the `id` property in a subsequent `search_type=product` requests' `product_id` field to request data from that individual product's landing page.

  


Not all results on Google Shopping have an individual product landing page, so you can use the `has_product_page` property to determine whether a product page is available.



[Read More](https://www.scaleserp.com/docs/search-api/results/shopping-results)Enhancement#### Video results - "date\_utc" and "domain" fields added

Two news fields have been added to the Google Video results - `domain` and `date_utc` (date UTC is an API-parsed ISO timestamp for the relative date time - i.e. "5 hours ago" shown next to the Google Video result).



[Read More](https://www.scaleserp.com/docs/search-api/results/video-results)New Feature#### "Related Products" added to the Google Products API results

Related Products, as shown in the carousel on the Google Product landing page, have been added to the `search_type=product` request. Price, rating, link, image and product title are retrieved.



[Read More](https://www.scaleserp.com/docs/search-api/results/product-results)![]()Enhancement#### Filter Batches by Last Run date

The Batches List API has been updated to allow sorting Batches by `last_run` date. You can also now filter the Batches by date using the `last_run_before` and `last_run_after` request parameters.

The Batches Dashboard has also been updated to show the Last Run date for each Batch.



[Read More](https://www.scaleserp.com/docs/batches-api/batches/list)![]()### August 2021

Update TypeDetailEnhancement#### Per-minute Batch scheduling improvements

The Per X Minutes Batch scheduling options have been extended to allow you to run Batches on a "Per X Minute" schedule restricted to specific hours of the day and days of the week or month.

The `schedule_hours`, `schedule_days_of_week` and `schedule_days_of_month` can now be used with `schedule_type=minutes` Batches for additional flexibility.

This allows for scenarios such as "run this Batch every 5 minutes, between 9am and 5pm, on weekdays only".



[Read More](https://www.scaleserp.com/docs/batches-api/batches/create)![]()New Feature#### Run Batches on a per-minute schedule

Batches can now be scheduled on a per-minute basis, in addition to the existing hourly, daily, weekly and monthly schedules.

Set `schedule_type=minutes` when creating your Batch and specify the per-minute schedule using the `schedule_minutes` parameter.

Per-minute schedules of every minute up to every hour are supported.



[Read More](https://www.scaleserp.com/docs/batches-api/batches/create)![]()New Feature#### Account Balance added to Account API

The Account API has been updated to include your current Account Balance in the `account_balance_usd` property. Your Account Balance is used to settle any Overage charges (to avoid multiple small overage charges being made to your payment card). You can top up your Account Balance at any time on the Account page of the Dashboard.



[Read More](https://www.scaleserp.com/docs/account-api)New Feature#### Grouped "related searches"

Scale SERP will now return expanded related searches (in addition to the standard related searches already returned) that are grouped under a particular group heading. New properties have been added to the related searches array showing the group name and type. Regular related searches will have `type=standard` and grouped related searches will have `type=group`. When `type=group` then the `group_name` property is populated.



[Read More](https://www.scaleserp.com/docs/search-api/results/related-searches)![]()New Feature#### Local Service Sponsored Ads parsing added

Local Service Ads parsing has been added to the API's response and is exposed in the `local_service_ads` property.



[Read More](https://www.scaleserp.com/docs/search-api/results/local-service-ads)![]()Enhancement#### Rich snippets attributes extraction

Parsing of the name/value pair attributes from the rich snippet section of organic results has been added to the API's parsing.



[Read More](https://www.scaleserp.com/docs/search-api/results/organic-results)![]()New Feature#### New Batches API endpoint to Stop All queued and running Batches

The new [Stop All Batches API](https://www.scaleserp.com/docs/batches-api/batches/stop-all) endpoint allows you to stop all `running` and `queued` Batches on your account in one API call. Useful if you have accidentally started a large number of Batches and need a quick way to set them all back to `idle`.



[Read More](https://www.scaleserp.com/docs/batches-api/batches/stop-all)### July 2021

Update TypeDetailNew Feature#### Android and iPhone browsers available for mobile SERP parsing

The new `mobile_type` parameter allows you to choose to execute your `device=mobile` requests using an Android or iPhone mobile browser.

![]()We started publishing Product Updates in June 2021, please refer to update emails for updates before this date.


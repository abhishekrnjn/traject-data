Batch Limits
------------

SerpWow imposes the following limits on Batches. If you wish to discuss changing a particular limit on your account please contact [hello@serpwow.com](mailto:hello@serpwow.com)

| Resource | Limit |
| --- | --- |
| Batches per Account | 10,000You can have up to 10,000 Batches set up on your account at any one time. To add more you should delete old or unused Batches. |
| Searches per Batch | 15,000 when using include\_html=false100 when using include\_html=trueNote When adding searches with include\_html=true to a Batch the maximum number of searches is lower (100) because including the HTML within the response makes the Batch Result Sets much larger. The limit is in place to ensure Result Set files are of a manageable size. If you have need to run a large number of searches all with include\_html=true then simply split the searches across multiple 100-search Batches.Note When adding searches with the max\_page parameter (for Automatic Pagination) the total requests in a Batch is the combination of max\_page X number of searches.For example, for a Batch populated with searches with max\_page=10 set the maximum number of searches that could be added to the Batch would be 1,500 (rather than 15,000). |
| Searches Added per API Request | 1,000Add 1,000 searches per API request, up to the maximum of 15,000. |
| Searches Added per Bulk CSV Upload | 15,000 |
| Automatic Pagination | When adding searches with the max\_page parameter set (for automatic pagination) the maximum max\_page value is 100 (meaning for each request up to 100 pages will be automatically retrieved). |
| Batches Expire After | 2 monthsAny Batch that has not been started for over 2 months is automatically deleted. Batches can be set to expire sooner on the Profile page of the Dashboard. |
| Result Sets Expire After | 14 daysResult Sets are available to download for 14 days. |
| Concurrently Running Batches | 5 for Batches with up to 250 Searches1 for Batches with greater than 250 SearchesCustomized concurrency settings can be arranged on request. If you have a specific thruput requirement required please contact our Support Team to discuss. |
| Queued Batches | There is no limit on the number of Batches you can start. They will be queued until a slot to process them is available. |
| Execution Speed | SerpWow runs all Searches within a Batch concurrently. As a guide, a Batch containing the maximum 15,000 Searches will take 2-3 minutes to return results. |

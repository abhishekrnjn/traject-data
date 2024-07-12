Pagination
----------

Requesting paginated results across multiple pages is one of the most common use-cases in Scale SERP.

For certain types of searches Scale SERP allows you to return data across multiple pages automatically.

You can request a single page per-search, or have Scale SERP automatically retrieve data from multiple pages and concatenate the results into one response.



**API Credits and `max_page`**  
Each successfully retrieved page incurs an API credit.  
  
If the request yields fewer pages than specified, only credits for the actual number of returned pages are charged. For example, for a request with `max_page=5` that only yields 3 pages (because only 3 pages are available), then only 3 API credits are charged.### Single Pages

To request a single page of results you should use the `page` parameter. For example, making a request with `page=5` will return data from page 5.

To find the total number of pages, and determine whether a next page is available, inspect the `pagination` object in the result JSON.



**Infinate Scrolling Pagination**  
Request types that implement infinate-scrolling pagination use a `next_page_token` parameter to request the next page of results. In these cases starting pagination from an explicit page number is not possible.### Multiple Pages

Scale SERP provides the `max_page` parameter to retrieve mutliple pages of results and concatenate them into one response - automating workloads such as "get the first 5 pages of results, if they exist".

When running a request with `max_page` set, the main array property of the response contains a concatenation of the array values from all requested pages.

#### Setting a Max Page

When using `max_page` Scale SERP will retrieve the number of pages (if available) specified in the `max_page` parameter. Results from subsequent pages will be concatenated into the main array property of the response. For example, the following request would yield data from pages 1, 2, 3, 4 and 5:

`max_page=**5**`The main array property of a request made with `max_page` will have the following properties added, making it easy to determine which physical page the current result came from:

PropertyTypeDescriptionpositionnumberThe position of the current result on the its page.pagenumberThe page the current result is taken from.position\_overallnumberThe position of the current result within all requested pages set in the `max_page` parameter.  
  
**Example** Assuming 10 results per page and a request made with `max_page=2` the first result on page would be `position_overall=1` and the last result on page 2 would be `position_overall=20`#### Setting the Start Page

Set the page to start the multiple-page concatenation from by using the `page` and `max_page` parameters together. For example, the following request would yield data from pages 2, 3 & 4:

`page=**2**&max_page=**4**`#### Limits when using `max_page`

Set the page to start the multiple-page concatenation from by using the `page` and `max_page` parameters together. For example, the following request would yield data from pages 2, 3 & 4:

Real-Time Searches5  
You can set a maximum `max_page` value of `5` when making real-time searches.  
  
**Note on `output=html`**  
When using `max_page` in combination with `output=html` the resultant HTML returned will consist of each page of HTML, delimited by a horizontal line break (`---` HTML tag).  
  
**Note on `include_html=true`**  
When using `max_page` in combination with `include_html=true` the `html` field is returned as an array containing the HTML of each returned page.Searches in Batches100  
You can set a maximum `max_page` value of `100` when adding searches to Searches.  
  
**Batch limits when using `max_page`**  
Using `max_page` on searches added to a Batch limits the total number of searches that can be added. See [Batch Limits](/docs/batches-api/limits) for more information.
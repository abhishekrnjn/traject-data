Google Product Reviews Results
------------------------------

DESKTOPTABLETMOBILEThe Google Product Reviews results are returned when making a request with `search_type=product` and `product_type=reviews` to retrieve product reviews results for a given product ID. The product ID is specified in the `product_id` parameter and you should also specify a `location` parameter to geo-locate the request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

Google Product IDs are returned by [Google Shopping search](/docs/search-api/results/google/shopping) requests.

![]()Google Product Reviews ResultsBelow is an example of how product reviews results are represented in the Scale SERP result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"product\_results":{...}}Copy### 

Scale SERP returns the following properties for `search_type=product` and `product_type=reviews` requests:

PropertyTypeDescriptionproduct\_resultsobjectproduct\_idstringThe product ID.reviewsarray**Reviews Array**An array of objects containing the product reviews.positionstringThe position of the review on the current page.titlestringThe title of the review.ratingnumberThe customer rating, out of 5, given alongside the review.datestringThe date of the review, as a locale-specific string.sourcestringThe source name of the source of the review.provided\_bystringWho the review was provided by, if shown.bodyobjectThe body text of the review.overviewobject**Overview Object**An object containing overview details of the product to whom the reviews belong.ratingnumberThe customer rating of this product, out of 5.review\_countnumberThe number of customer reviews this product has received.per\_starobjectAn object showing the number of customer reviews at each star rating this product has received. Contains the following properties `one_star`, `two_star`, `three_star`, `four_star` and `five_star`.  
  
![]()paginationobject**Pagination Object**An object containing pagination details for the product reviews.next\_page\_tokennumberA token that can be passed in a subsequent `product_type=reviews` request to provide the next page of Product Reviews results.  
  
**Note** Product Review results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead the `next_page_token` can be passed in to the `next_page_token` request parameter to retrieve the next page of Product Reviews results.Next Steps

* [Google Product Reviews Parameters](/docs/search-api/searches/google/product-reviews)

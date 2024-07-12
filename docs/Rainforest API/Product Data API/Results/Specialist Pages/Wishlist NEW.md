Wishlist Results
----------------

When making a request with the `type` [parameter](/docs/product-data-api/parameters/wishlist) set to `type=wishlist` Rainforest API will return data from the Wishlist page for the wishlist specified in either the `wishlist_id` and `amazon_domain` parameters or the `url` parameter.

Wishlist data is retrieved from the [Wishlist popup](https://www.amazon.com/hz/wishlist/ls/38B3V3AT7UH9B).

![]()Wishlist PageAn example of the JSON object returned from a Wishlist request is shown below:

{"wishlist\_results":[...]"pagination":{...}}CopyRainforest API returns the following properties for Wishlist requests:



**Paginating Results**  
Amazon returns 10 Wishlist per page. To request more wishlist results issue additional requests passing the `next_page_token` parameter from the previous request.  
  
**Note** due to the infinate-scrolling behaviour of wishlist pages, you cannot reference a specific page directly. Pagination is achieved via the `next_page_token` request parameter.PropertyTypeDescriptionwishlist\_resultsarrayAn array of Wishlist objects, containing each of the Wishlist items shown on the Wishlist popup. The Wishlist object has the following properties:  
positionnumberThe position (1-based) of the wishlist item on the current page.titlestringThe title of the wishlist item.linkstringA link to the product page for the wishlist item ASIN.asinstringThe ASIN of the wishlist item.imagestringAn image URL to the image of the wishlist item, if shown.ratingnumberAn rating of the image of the wishlist item, if shown.ratings\_totalnumberAn total number of customer ratings the wishlist item has received, if shown.in\_stockbooleanSet to `true` when the wishlist item is in stock, `false` otherwise.prioritystringThe priority of the wishlist item, as shown on the wishlist page - i.e. `medium`.requested\_countnumberThe number of this wishlist item that has been requested by the wishlist owner.purchased\_countnumberThe number of this wishlist item that have been purchased so far.added\_dateobjectAn date the wishlist item was added to the wishlist. Contains a `raw` and `utc` (timestamp) property.priceobject**Price Object**The price object contains details about the wishlist items pricing.symbolstringThe currency symbol, i.e. `$` for USD.valuenumberThe price of the wishlist item.currencystringThe currency of the wishlist item as a [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) currency code.rawstringThe raw price as displayed on the wishlist item.paginationobjectAn object containing details of the `next_page_token` required to request the next page of wishlist results in a subsequent requests' `next_page_token` [parameter](/docs/product-data-api/parameters/wishlist).  
next\_page\_tokennumberThe next page token to pass into a subsequent `type=wishlist` requests' `next_page_token` [request parameter](/docs/product-data-api/parameters/wishlist).Next Steps

* [Wishlist Parameters](/docs/product-data-api/parameters/wishlist)

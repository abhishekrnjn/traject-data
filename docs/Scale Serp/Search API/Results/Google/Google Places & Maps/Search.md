Google Places Results
---------------------

DESKTOPTABLETMOBILEScale SERP parses Google Local & Maps results (i.e. local business listings) when the `search_type` [search parameter](/docs/search-api/searches/google/places) is set to `search_type=places`. When this parameter is set Scale SERP provides a `places_results` array in the result JSON that contains the Local or Maps results.

The nature of the value passed in the `location` parameter determines whether results are returned from Google Local, or Google Maps. For full details see the [request parameter documentation](/docs/search-api/searches/google/places).

### Google Local Results

If the `location` parameter is set to a location name from the [Locations API](/docs/locations-api/overview) (or any other free-form location name text) - for example `Manhattan,New+York,United+States` then results will be returned from a [Google Local](https://www.google.com/search?q=pizza&gl=us&hl=en&uule=w+CAIQICIgTWFuaGF0dGFuLE5ldyBZb3JrLFVuaXRlZCBTdGF0ZXM&tbm=lcl) page.

![]()Google Local PageBelow is an example of the `search_type=places` response when requesting [Google Local](https://www.google.com/search?q=pizza&gl=us&hl=en&uule=w+CAIQICIgTWFuaGF0dGFuLE5ldyBZb3JrLFVuaXRlZCBTdGF0ZXM&tbm=lcl) results.

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"places\_results":[...]"pagination":{...}}Copy### Google Maps Results

If the `location` parameter is set to a latitude, longitude and zoom value - for example `location=lat:43.437677,lon:-3.8392765,zoom:15` then results will be returned from a [Google Maps](https://www.google.com/maps/search/pizza/@43.437677,-3.8392765,15z) page.



**Pagination with Google Maps**  
When requesting Google Maps results (i.e. when specifying your `location` parameter using a latitude, longitude and zoom level) Google do not display the total number of pages of result available (as the Google Maps interface allows the user to infinately scroll and move the map to generate more results).  
  
Therefore when showing Google Maps results the `pagination` section of the results JSON is not present. To paginate through Google Maps results simply specify additional requests, incrementing your requests' `page` parameter each time (`page=2`, `page=3` etc) until no `place_results` array is present in the result JSON (this indicates you have reached the end of the available results for the given latitude, longitude and zoom level).![]()Google Maps PageBelow is an example of the `search_type=places` response when requesting [Google Maps](https://www.google.com/maps/search/pizza/@43.437677,-3.8392765,15z) results.

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"places\_results":[...]}Copy### 

Scale SERP returns the following properties for `search_type=places` requests (any differences between the [Google Local](https://www.google.com/search?q=pizza&gl=us&hl=en&uule=w+CAIQICIgTWFuaGF0dGFuLE5ldyBZb3JrLFVuaXRlZCBTdGF0ZXM&tbm=lcl) and [Google Maps](https://www.google.com/maps/search/pizza/@43.437677,-3.8392765,15z) results are noted below):

PropertyTypeDescriptionsearch\_informationobjectAn object containing top-level details about the search.  
original\_query\_yields\_zero\_resultsstringSet to `true` when the original `search_term` supplied in the request yielded no results and Google "corrected" it.query\_displayedstringThe query / search term displayed in the search bar.places\_resultsarrayAn array of Places Result objects, containing each of the place results shown on the results page. The Place Result object has the following properties:  
positionnumberThe position of the place result **within the current page of results**.titlestringThe title of the place result.data\_cidstringThe `cid` of the place result. A CID (Customer ID Number) is a unique identifier Google assigns to a specific businesses entity. Read more about Google `cid`'s [here](https://morecustomersmoresales.com.au/google-my-business-cid-placeid-fid-mreid/).  
**Note** The `data_cid` is used as a request parameter in [Place Details](/docs/search-api/searches/google/place-details) and [Place Products](/docs/search-api/searches/google/place-products) requests.  
data\_idstringAn additional hexidecimal-encoded ID useful for some SEO applications.  
**Note** The `data_id` is used as a request parameter in [Place Details](/docs/search-api/searches/google/place-details), [Place Photos](/docs/search-api/searches/google/place-photos), [Place Reviews](/docs/search-api/searches/google/place-reviews) and [Place Posts](/docs/search-api/searches/google/place-posts) requests.linkstringA link to the website of the place result, if shown. If the link is not shown on the Places search results page you pay perform a [Place Details](/docs/search-api/searches/google/place-details) request, passing in the `data_cid` of this Place, to retrieve it from the Place Details popup.thumbnailstringA URL to the thumbnail preview image next to the place result (if shown). May also be returned as a Base64 encoded image.addressstringThe street address of the place result.pricestringA locale-specific string (i.e. "$$$") indicating the relative price of services offered by the business.price\_parsednumberA numeric representation of the relative price of services offered by the business, ranging from `1` (inexpensive) to `5` (expensive).price\_descriptionstringA text representation of the relative price of services offered by the business, if shown. For example 'Inexpensive'.ratingnumberThe customer rating the place has received, out of 5.reviewsnumberThe number of customer reviews the place has received.categorystringThe text-representation of the place category - i.e. "Coffee Shop".all\_categoriesarrayAn array of strings for each of the place categories, if more than one exist and are shown.gps\_coordinatesobjectAn object containing `latitude` and `longitude` number properties being the latitude and longitude of the place result.descriptionstringThe full-text description of the place result, if shown.extensionsarrayAn array of strings being the extensions/services offered by the business, i.e. "Offers takeaway".phonestringThe phone number of the business in the place result, if shown. If the phone is not shown you may find a [Place Details](/docs/search-api/searches/google/place-details) request returns it from the Place Details page.user\_reviewstringThe full-text of the user review next to the place result (if shown).**Note that user reviews are only shown on `search_type=places` on Google Maps, not Google Local**. To retrieve full Place Reviews use the [Place Reviews](/docs/search-api/searches/google/place-reviews) request.paginationobjectAn object containing pagination details for making subsequent requests for additional pages of results.  
  
**Note** the `pagination` object is only returned for [Google Local](https://www.google.com/search?q=pizza&gl=us&hl=en&uule=w+CAIQICIgTWFuaGF0dGFuLE5ldyBZb3JrLFVuaXRlZCBTdGF0ZXM&tbm=lcl) results. See the note on Pagination above for information on how to paginate [Google Maps](https://www.google.com/maps/search/pizza/@43.437677,-3.8392765,15z) requests.  
currentnumberThe current page number.nextstringThe Google URL for the next page of requests.other\_pagesobjectA dictionary, keyed by the page number, of Google URLs to all other pages shown on the current page of results.api\_paginationobjectAn object containing `next` and `other_pages` properties being mirrors of the `next` and `other_pages` properties with API URLs instead of Google URLs. Provided as a convenience for making additional API requests.Next Steps

* [Google Places Parameters](/docs/search-api/searches/google/places)

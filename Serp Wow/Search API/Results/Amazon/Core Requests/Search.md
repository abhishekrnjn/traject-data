Amazon Search Results
---------------------

DESKTOPTABLETMOBILESerpWow parses Amazon search results when the `engine=amazon` request parameter is set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/amazon_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Amazon Search ResultsBelow is an example of how Amazon search results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"amazon\_results":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `engine=amazon` requests:

| Property | Type | Description |
| amazon\_results | array | An array of Search Result objects, containing each of the product results shown on the Search Results page. The Search Result object has the following properties:positionnumberThe position of the result on the search results page.titlestringThe product name.brandstringThe product brand (where shown, note that not all search results page layouts break out the brand separately to the title).asinstringThe Amazon product ID (ASIN) for the product.linkstringThe product page link.is\_primebooleanDetermines whether the product is Prime-eligible or not.is\_amazon\_freshbooleanDetermines whether the product is an Amazon Fresh product, or not.is\_whole\_foods\_marketbooleanDetermines whether the product is a Whole Foods Market product, or not.couponobject| Coupon Object | Present when the "Coupon" badge is shown next to the search result. Contains the following properties: |
| --- | --- |
badge\_textstringThe text shown inside the coupon badge (i.e. "Save 5%").textstringThe text shown next to the coupon badge (i.e. "with coupon").dealobject| Deal Object | Present when the "Deal" badge is shown next to the search result. Contains the following properties: |
| --- | --- |
linkstringA link to the deal landing page.textstringThe text shown next to the deal badge (i.e. "Limited time deal").badge\_textstringThe text shown inside the deal badge (i.e. "16% off").gift\_guideobject| Gift Guide Object | Present when the "Gift Guide" badge is shown next to the search result. Contains the following properties: |
| --- | --- |
linkstringA link to the deal landing page.badge\_textstringThe text shown inside the gift guide badge (i.e. "Holiday gift guide"). Can be useful in determining the "type" of gift guide the search result appears in.amazons\_choiceobject| Amazons Choice Object | Present when the "Amazon's Choice" badge is shown next to the search result. Contains the following properties: |
| --- | --- |
linkstringA link to the product.keywordsstringThe keywords for which this search result is "Amazon's Choice".bestsellerobject| BestSeller Object | Present when the "BestSeller" badge is shown next to the search result. More detailed bestseller information can be retrieved from the product page by making a type=product request specifying this search results ASIN. Contains the following properties: |
| --- | --- |
linkstringA link to the Bestsellers page to which this bestseller badge relates.categorystringThe category name for which this product is a best seller, i.e. "USB Cables".imagestringA link to the image of the product.sponsoredbooleanSet to true or false depending on whether the search result is a sponsored listing, or not.authorsarray| Authors Array | The authors property contains the authors or artists of the product. Mainly applies to books, music and video products. The author object has the following properties: |
| --- | --- |
namestringThe name of the author or artist.linkstringThe link to the author or artist on the Amazon domain, if present.add\_on\_itemobject| Add-On Item Object | The add-on item object is present when the item is part of the Amazon 'add-on item' program. The property will be omitted if the product is not an add-on item. |
| --- | --- |
is\_add\_on\_itembooleanTrue/false indicating whether the product is an add-on item.availabilityobject| Availability Object | The Availability object is present when Amazon show availability (i.e. stock level) data next to the search reult. The availability property will be omitted if availability information is not shown alongside the search result. The availability object contains the following properties: |
| --- | --- |
rawstringThe raw availability as shown next to the search result, for example "Only 1 left in stock - order soon".categoriesarray| Categories Array | An array containing details of the categories shown with this product as displayed next to the search bar at the top of the page. Each object in the array contains the following properties: |
| --- | --- |
namestringThe name of the category (i.e. "Toys & Games").ratingnumberThe overall rating of the product, out of 5.ratings\_totalnumberThe total number of customer ratings the product has received.deliveryobject| Delivery Object | The Delivery object is present when Amazon show delivery information neat to the search result. The delivery object contains the following properties: |
| --- | --- |
taglinestringA string containing the tagline associated with the delivery option, for example "Get it as soon as Sat, Oct 3".priceobjectA price object representing the price and currency of the delivery option. The delivery price object has the same properties as the price objects in the prices arrayis\_carouselbooleanSet to true when this search result is part of a carousel. It is not present if the search result is not part of a carousel. If is\_carousel=true then the carousel property describes the properties of the carousel this search result if part of.carouselobject| Carousel Object | When a search result is part of a "carousel" (a horizontally scrolling row of search results nested within the main search results) then the carousel object is present. The carousel object contains details of the carousel that this search result is part of. Examples of carousels could be "Highly Rated" or "Today's Deals". The carousel object contains the following properties: |
| --- | --- |
titlestringThe title of the carousel that this search result is part of, for example "Highly Rated".sub\_titlestringThe subtitle of the carousel that this search result is part of, for example "Based on star rating and number of customer ratings".sponsoredbooleanSet to true when the carousel itself (as-shown in the carousel header section) indicates that the contents of the carousel are all sponsored results.idbooleanThe ID of the carousel that this search result is part of.total\_itemsbooleanThe total number of items in the carousel that this search result is part of.pricesarray| Prices Array | The prices array contains details about the products pricing, as shown underneath the product title. It is an array of price objects, the properties of which are described below: |
| --- | --- |
symbolstringThe currency symbol, i.e. $ for USD.valuenumberThe price of the Offer.currencystringThe currency of the Offer as a ISO 4217 currency code.rawstringThe raw price as displayed on the Offer listing.namestringThe name of the price if applicable, for example "Kindle", "Hardcover".priceobjectA price object representing the first item in the prices array. This is normally the "main" price for the product and is included as a convienience to make extracting the main price easier.informationstringThe information text, typically shown in bold below the product title and showing the pack quantity. For example 25.4 Fl Oz (Pack of 2).unit\_pricestringThe product unit price, where shown. For example $0.57/Fl Oz. |
| pagination | object | An object containing details of the pagination section of the page.currentnumberThe current page number, if shown.totalnumberThe total number of pages available, if shown. |
Next Steps

* [Amazon Search Parameters](/docs/search-api/searches/amazon/search)

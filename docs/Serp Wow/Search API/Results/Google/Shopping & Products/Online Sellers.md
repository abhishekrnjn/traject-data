Google Product Online Sellers Results
-------------------------------------

DESKTOPTABLETMOBILEThe Google Product Online Sellers results are returned when making a request with `search_type=product` and `product_type=sellers_online` to retrieve product online sellers results for a given product ID. The product ID is specified in the `product_id` parameter and you should also specify a `location` parameter to geo-locate the request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

Google Product IDs are returned by [Google Shopping search](/docs/search-api/results/google/shopping) requests.

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_product_online_sellers.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Product Online Sellers ResultsBelow is an example of how product online sellers results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"product\_results":{...}}Copy### 

SerpWow returns the following properties for `search_type=product` and `product_type=sellers_online` requests:

| Property | Type | Description |
| product\_results | object | product\_idstringThe product ID.sellers\_onlinearray| Sellers Online Array | An array of objects containing the online sellers for this product. |
| --- | --- |
positionstringThe position of the online seller offer on the current page.merchantstringThe merchant name of the merchant.merchant\_ratingnumberThe merchant rating, out of 5.merchant\_reviewsnumberThe number of reviews this merchant has received.linkstringA link to the website of the merchant, note that this is typically shown as a tracking link (instead of a direct link to the merchant website).base\_price\_rawstringThe raw base price string as shown next to the seller offer. The base price is typically the price before shipping and tax.base\_price\_parsedobjectAn object showing the parsed base price. Parsing is locale-specific and may not be universal or available across all locales. Contains the following properties: currency (the 3-letter currency code), symbol (the currency symbol), value (the parsed number-value of the price), raw (the raw string representation of the price).shipping\_price\_rawstringThe raw shipping price string as shown next to the seller offer.shipping\_price\_parsedobjectAn object showing the parsed shipping price.tax\_price\_rawstringThe raw tax price string as shown next to the seller offer.tax\_price\_parsedobjectAn object showing the parsed tax price.total\_price\_rawstringThe raw total price string as shown next to the seller offer.total\_price\_parsedobjectAn object showing the parsed total price. |
Next Steps

* [Google Product Online Sellers Parameters](/docs/search-api/searches/google/product-online-sellers)

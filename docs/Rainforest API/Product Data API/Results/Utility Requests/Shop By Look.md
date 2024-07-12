Shop By Look Results
--------------------

When making a request with the `type` [parameter](/docs/product-data-api/parameters/shop-by-look) set to `type=shop_by_look` Rainforest API will return a page of Shop By Look products for the product specified in the `asin`.

Shop By Look details are retrieved from the [product page](https://www.amazon.de/dp/B087CLWH69) for a single product on Amazon. An `type=shop_by_look`. The first page of Shop By Look results are always returned with `type=product` requests (to the product page). The purpose of the dedicated `type=shop_by_look` request is to allow pagination through all pages of Shop By Look results.

**Note** that the 1st ASIN returned by a Shop By Look request is always the original ASIN specified in the `asin` request parameter. A maximum of 12 Shop By Look ASINs are returned per request.

![]()Shop By Look SectionAn example of the JSON object returned from an Shop By Look request is shown below:

{"request\_info":{...}"request\_metadata":{...}"request\_parameters":{...}"shop\_by\_look":[...]}CopyRainforest API returns the following properties for Shop By Look requests:

PropertyTypeDescriptionshop\_by\_lookArraypositionintegerThe position of the current result within the current page.asinstringThe ASIN of the product.is\_primebooleanTrue / false depending on whether the ASIN is marked as Prime, or not.imagestringA link to the image of the product.ratingnumberThe overall rating of the product, out of 5.ratings\_totalnumberThe total number of customer ratings the product has received.priceobjectA price object describing the price of the product.Next Steps

* [Shop By Look Parameters](/docs/product-data-api/parameters/shop-by-look)

Also Bought Results
-------------------

When making a request with the `type` [parameter](/docs/product-data-api/parameters/also-bought) set to `type=also_bought` Rainforest API will return details of the "also-bought" products for the product specified in either the `asin` and `amazon_domain` parameters or the `url` parameter.

Also bought details are retrieved from the [product page](https://www.amazon.com/dp/B084ZF5D65) for a single product on Amazon. An `type=also_bought` request will automatically paginate through all of the pages of also-bought data and return every also bought result.

![](https://apiimages.imgix.net/rainforestapi/images/png/docs/also_bought.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Also Bought SectionAn example of the JSON object returned from an Also Bought request is shown below:

{"request\_info":{...}"request\_metadata":{...}"request\_parameters":{...}"also\_bought":[...]}CopyRainforest API returns the following properties for Also Bought requests:

PropertyTypeDescriptionalso\_boughtarrayAn array containing details of the other products that Amazon customers bought alongside the current product. Each object in the array contains the following properties:  
titlestringThe title of the product.linkstringThe link to the product page.asinstringThe ASIN of the product.imagestringA link to the image of the product.ratingnumberThe overall rating of the product, out of 5.ratings\_totalnumberThe total number of customer ratings the product has received.priceobjectA price object describing the price of the product.Next Steps

* [Also Bought Parameters](/docs/product-data-api/parameters/also-bought)

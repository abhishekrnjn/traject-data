Google Product Specifications Results
-------------------------------------

DESKTOPTABLETMOBILEThe Google Product Specifications results are returned when making a request with `search_type=product` and `product_type=specifications` to retrieve product specifications results for a given product ID. The product ID is specified in the `product_id` parameter and you should also specify a `location` parameter to geo-locate the request (locations can be retrieved via the [Locations API](/docs/locations-api/overview)).

Google Product IDs are returned by [Google Shopping search](/docs/search-api/results/google/shopping) requests.

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_product_specifications.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Product Specifications ResultsBelow is an example of how product specifications results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"product\_results":{...}}Copy### 

SerpWow returns the following properties for `search_type=product` and `product_type=specifications` requests:

| Property | Type | Description |
| product\_results | object | product\_idstringThe product ID.titlestringThe product name/title as shown at the top of the product specifications page.descriptionstringThe product description as shown at the top of the product specifications page.specificationsarray| Specifications Array | An array of objects containing the product specifications. |
| --- | --- |
idstringThe locale-specific ID of the specification.namestringThe specification name.valuenumberThe specification value.category\_idstringThe locale-specific ID of the category to which this specification belongs. This is typically the header text of the specification section.categorystringThe category name of the category this specification belongs to. |
Next Steps

* [Google Product Specifications Parameters](/docs/search-api/searches/google/product-specifications)

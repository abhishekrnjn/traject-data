Google Place Products Results
-----------------------------

DESKTOPTABLETMOBILESerpWow parses the Place Products results the `place_products_results` array in the JSON output when the `search_type=place_products` request parameter is set and the `data_cid` request parameter is set to a valid `data_cid` as-returned by a `search_type=places` [Places requests](/docs/search-api/searches/google/places).

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_place_products.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Place Products ResultsBelow is an example of how the Place Products are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"place\_products\_results":[...]}Copy### 

SerpWow returns the following properties for `search_type=place_products` requests:

| Property | Type | Description |
| place\_products\_results | array | An array of Place Product result objects, containing each of the Place Product results returned. The Place Product Result object has the following properties:namenumberThe name of the place product.linkstringA link to the place product landing page.imagestringAn image URL to the place product image.pricestringThe raw price (as a locale-specific string), if shown, of the place product.positionnumberThe position of the place product in the place\_products\_results array. |
Next Steps

* [Google Place Products Parameters](/docs/search-api/searches/google/place-products)

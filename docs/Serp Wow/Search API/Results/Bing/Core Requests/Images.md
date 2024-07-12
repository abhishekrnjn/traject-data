Bing Image Results
------------------

DESKTOPTABLETMOBILESerpWow parses Bing Image search results when the `engine=bing` and `search_type=images` search parameters are set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/bing_images.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Bing Image ResultsBelow is an example of how the Bing Image results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"image\_results":[...]}Copy### 

SerpWow returns the following properties for Bing Image requests:

| Property | Type | Description |
| image\_results | array | An array of Image Result objects, containing each of the image results returned. The Image Result object has the following properties:positionnumberThe position of the image result on the current page.titlestringThe title of the image result.linkstringA link to the image result.domainstringThe domain of the link to the image result.widthnumberThe width of the image in pixels, if shown.heightnumberThe height of the image in pixels, if shown.imagestringThe thumbnail image of the image result, either returned as a URL to the image, or as a Base64-encoded image string.descriptionstringThe text description next to the image result, if shown.image\_typestringThe type of the image result - i.e. "jpeg", if shown.sourceobjectAn object with name, link and domain properties describing the source of the image, if shown. |
Next Steps

* [Bing Image Parameters](/docs/search-api/searches/bing/images)

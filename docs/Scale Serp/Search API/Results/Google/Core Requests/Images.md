Google Image Results
--------------------

DESKTOPTABLETMOBILEScale SERP parses the Google image search results the`image_results`array in the JSON output when the `search_type=images` search parameter is set.

![](https://apiimages.imgix.net/scaleserp/images/png/docs/google_images.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Image ResultsBelow is an example of how the`image_results`array is represented in the Scale SERP result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"image\_results":[...]"top\_carousel":{...}}Copy### 

Scale SERP returns the following properties for `search_type=images` requests:

PropertyTypeDescriptionimage\_resultsarrayAn array of Image Result objects, containing each of the image results returned. The Image Result object has the following properties:  
positionnumberThe position of the image result on the current page.titlestringThe title of the image result.linkstringA link to the image result.domainstringThe domain of the link to the image result.widthnumberThe width of the image in pixels, if shown.heightnumberThe height of the image in pixels, if shown.imagestringThe thumbnail image of the image result, either returned as a URL to the image, or as a Base64-encoded image string.brandstringThe brand name of the image result, if shown.top\_carouselobjectAn object containing details of the "top carousel" section at the top of the images SERP page.  
![]()  
categorystringThe category or title of the top carousel, if one is shown.itemsarray**Items Array**An array containing the items in the top carousel:titlestringThe title text of the top carousel item, if shown.subtitlestringThe sub-title text of the top carousel item, if shown.linkstringThe link of the top carousel item, if shown.block\_positionnumberThe position of the top carousel item, relative to other page features shown.Next Steps

* [Google Image Parameters](/docs/search-api/searches/google/images)

Google Place Photos Results
---------------------------

DESKTOPTABLETMOBILESerpWow parses the Place Photos results the `place_photos_results` array in the JSON output when the `search_type=place_photos` request parameter is set and the `data_id` request parameter is set to a valid `data_id` as-returned by a `search_type=places` [Places requests](/docs/search-api/searches/google/places).

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_place_photos.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Place Photos ResultsBelow is an example of how the Place Photos are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"place\_photos\_results":[...]"categories":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `search_type=place_photos` requests:

| Property | Type | Description |
| place\_photos\_results | array | An array of Place Photo result objects, containing each of the Place Photo results returned. The Place Photo Result object has the following properties:thumbnailstringAn image URL to the thumbnail image of the place photo result.imagestringAn image URL to the full-size image of the place photo result. |
| categories | array | An array of Category objects. You can take the id of a category and pass it in to the category\_id parameter of a subsequent search\_type=place\_photos request to retrieve place photos belonging to that category.titlestringThe title of the category.idstringThe ID of the category. Can be passed in to the category\_id parameter of a subsequent search\_type=place\_photos request to retrieve place photos belonging to that category. |
| pagination | object | next\_page\_tokenstringA token that can be passed in a subsequent search\_type=place\_photos request to provide the next page of Place Photos results.Note Place Photo results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead the next\_page\_token can be passed in to the next\_page\_token request parameter to retrieve the next page of place photo results. |
Next Steps

* [Google Place Photos Parameters](/docs/search-api/searches/google/place-photos)

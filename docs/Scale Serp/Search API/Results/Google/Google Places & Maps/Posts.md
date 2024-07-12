Google Place Posts Results
--------------------------

DESKTOPTABLETMOBILEScale SERP parses the Place Posts results the `place_posts_results` array in the JSON output when the `search_type=place_posts` request parameter is set and the `data_id` request parameter is set to a valid `data_id` as-returned by a `search_type=places` [Places requests](/docs/search-api/searches/google/places).

![](https://apiimages.imgix.net/scaleserp/images/png/docs/google_place_posts.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Place Posts ResultsBelow is an example of how the Place Posts are represented in the Scale SERP result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"place\_posts\_results":[...]}Copy### 

Scale SERP returns the following properties for `search_type=place_posts` requests:

PropertyTypeDescriptionplace\_posts\_resultsarrayAn array of Place Post result objects, containing each of the Place Post results returned. The Place Post Result object has the following properties:  
namenumberThe name of the place post.linkstringA link to the place post page.imagestringAn image URL to the place post image.datestringThe raw date of the review.titlestringThe title text of the place post.bodystringThe body text of the place post, if shown.positionnumberThe position of the place post in the `place_posts_results` array.Next Steps

* [Google Place Posts Parameters](/docs/search-api/searches/google/place-posts)

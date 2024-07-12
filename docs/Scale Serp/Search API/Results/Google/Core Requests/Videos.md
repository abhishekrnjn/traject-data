Google Video Results
--------------------

DESKTOPTABLETMOBILEScale SERP parses the Google video search results the`video_results`array in the JSON output when the `search_type=videos` search parameter is set.

![](https://apiimages.imgix.net/scaleserp/images/png/docs/google_videos.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Video ResultsBelow is an example of how Google Video results are represented in the Scale SERP result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"video\_results":[...]"related\_searches":[...]"pagination":{...}}Copy### 

Scale SERP returns the following properties for `search_type=videos` requests:

PropertyTypeDescriptionvideo\_resultsarrayAn array of Video Result objects, containing each of the video results returned. The Video Result object has the following properties:  
positionnumberThe position of the video result on the current page.titlestringThe title of the video result.linkstringA link to the video result.domainstringThe domain of the link to the video result.displayed\_linkstringThe displayed (visual) link shown next to the video result.datestringThe raw date, if shown, of the video result.date\_utcstringThe parsed date, in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format, of the video result. Note that date parsing relies on the API being able to successfully parse the date and isn't guaranteed in all locales.snippetstringThe snippet text of the video result.imagestringThe thumbnail image of the video result, either returned as a URL to the image, or as a Base64-encoded image string.lengthstringThe runtime of the video, expressed in the form `minutes:seconds`.related\_searchesarrayAn array of Related Search objects, containing each of the related video searches shown at the bottom of the video results page. The Related Search object has the following properties:  
querystringThe keywords / search term of the related search.linkstringA link to the Google search URL for the related search.paginationobjectAn object containing details of the pagination section of the page. Details are provided as Google links and API links (to make sending paginated requests easier):  
currentnumberThe current page number, if shown.nextstringThe Google URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Google URL to the page.api\_paginationobjectAn object containing API links to request the next pages of results. Provided as a convenience to allow you to run subsequent requests for additional pages. Contains a `next` and `other_pages` property.Next Steps

* [Google Video Parameters](/docs/search-api/searches/google/videos)

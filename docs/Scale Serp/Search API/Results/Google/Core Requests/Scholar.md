Google Scholar Results
----------------------

DESKTOPTABLETMOBILEScale SERP parses the Google scholar search results the`scholar_results`array in the JSON output when the `search_type=scholar` search parameter is set.

![](https://apiimages.imgix.net/scaleserp/images/png/docs/google_scholar.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Image ResultsBelow is an example of how the`scholar_results`array is represented in the Scale SERP result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"scholar\_results":[...]"pagination":{...}"related\_searches":[...]}Copy### 

Scale SERP returns the following properties for `search_type=scholar` requests:

PropertyTypeDescriptionscholar\_resultsarrayAn array of Scholar Result objects, containing each of the scholar results returned. The Scholar Result object has the following properties:  
positionnumberThe position of the scholar result on the current page.titlestringThe title of the scholar result.linkstringA link to the scholar result.domainstringThe domain of the link to the scholar result.displayed\_linkstringThe displayed (visual) link shown next to the scholar result.snippetstringThe snippet text of the scholar result.cited\_by\_countnumberThe number of Cites the result has received.  
  
![]()cited\_by\_linkstringA Google link to the Cited By results.pdf\_linkstringA link to the PDF if shown with the result.versions\_countnumberThe number of Versions the result has.  
  
![]()versions\_linkstringA Google link to the Versions results.paginationobjectAn object containing details of the pagination section of the page. Details are provided as Google links and API links (to make sending paginated requests easier):  
currentnumberThe current page number, if shown.nextstringThe Google URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Google URL to the page.api\_paginationobjectAn object containing API links to request the next pages of results. Provided as a convenience to allow you to run subsequent requests for additional pages. Contains a `next` and `other_pages` property.related\_searchesarrayAn array of Related Search objects, containing each of the related searches shown at the bottom of the search results page. The Related Search object has the following properties:  
![]()  
querystringThe keywords / search term of the related search.linkstringA link to the Google search URL for the related search.Next Steps

* [Google Scholar Parameters](/docs/search-api/searches/google/scholar)

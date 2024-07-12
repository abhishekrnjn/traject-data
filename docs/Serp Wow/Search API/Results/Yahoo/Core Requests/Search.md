Yahoo Search Results
--------------------

DESKTOPTABLETMOBILESerpWow parses Yahoo search results when the `engine=yahoo` request parameter is set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/yahoo_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Yahoo Search ResultsBelow is an example of how Yahoo search results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"ads":[...]"organic\_results":[...]"local\_results":[...]"knowledge\_graph":{...}"pagination":{...}}Copy### 

SerpWow returns the following properties for `engine=yahoo` requests:

| Property | Type | Description |
| organic\_results | array | An array of Organic Result objects, containing each of the organic results returned. The Organic Result object has the following properties:positionnumberThe position of the organic result on the current page.titlestringThe title of the organic result.linkstringA link to the organic result.domainstringThe domain of the link to the organic result.displayed\_linkstringThe displayed (visual) link shown next to the organic result.snippetstringThe snippet text of the organic result. |
| local\_results | array | An array of Local Results objects, containing each of the local results returned. The Local Result object has the following properties:positionnumberThe position of the result on the current page.titlestringThe title of the result.linkstringA link to the result.addressstringThe address of the result.phonestringThe phone number of the result.ratingnumberThe review rating of the result.reviewsnumberThe review count of the result.pricestringThe price of the result ($, $$, etc).categorystringThe category of the result. |
| knowledge\_graph | object | The knowledge graph contains the following properties:titlestringThe title of the knowledge graph.websitestringThe website of the knowledge graph.descriptionstringThe description of the knowledge graph.addressstringThe address of the knowledge graph.phonestringThe phone number of the knowledge graph.ratingnumberThe review rating of the knowledge graph.reviewsnumberThe review count of the knowledge graph. |
| ads | array | An array of Ads objects, containing each of the sponsored ads shown on the Yahoo SERP. The Ad object has the following properties:positionnumberThe position of the ad result within the ads on the current page.titlestringThe title text of the ad.tracking\_linkstringThe tracking link that is followed when the Ad is clicked.displayed\_linkstringThe displayed (visual) link shown in the ad.descriptionstringThe descriptive text of the ad.block\_positionstringThe position of ad block this ad belongs to on the Yahoo SERP page. Can be set to top or bottom. |
| pagination | object | An object containing details of the pagination section of the page.currentnumberThe current page number, if shown.nextstringThe Yahoo URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Yahoo URL to the page. |
Next Steps

* [Yahoo Search Parameters](/docs/search-api/searches/yahoo/search)

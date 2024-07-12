Naver Search Results
--------------------

DESKTOPTABLETMOBILESerpWow parses Naver search results when the `engine=naver` request parameter is set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/naver_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Naver Search ResultsBelow is an example of how Naver search results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"ads":[...]"inline\_knowledge":[...]"organic\_results":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `engine=naver` requests:

| Property | Type | Description |
| organic\_results | array | An array of Organic Result objects, containing each of the organic results returned. The Organic Result object has the following properties:positionnumberThe position of the organic result on the current page.titlestringThe title of the organic result.linkstringA link to the organic result.domainstringThe domain of the link to the organic result.displayed\_linkstringThe displayed (visual) link shown next to the organic result.snippetstringThe snippet text of the organic result. |
| ads | array | An array of Ads objects, containing each of the sponsored ads shown on the Naver SERP. The Ad object has the following properties:positionnumberThe position of the ad result within the ads on the current page.titlestringThe title text of the ad.tracking\_linkstringThe tracking link that is followed when the Ad is clicked.displayed\_linkstringThe displayed (visual) link shown in the ad.descriptionstringThe descriptive text of the ad.block\_positionstringThe position of ad block this ad belongs to on the Naver SERP page. Can be set to top or bottom. |
| inline\_knowledge | array | An array of Inline Knowledge result objects, containing each of the inline knowledge results shown on the Naver SERP. The Inline Knowledge object has the following properties:positionnumberThe position of the inline knowledge result within the ads on the current page.titlestringThe title text of the inline knowledge result.linkstringThe link shown in the inline knowledge result (note that Naver normally shows internal redirect links, rather than the actual target URL).snippetstringThe descriptive text of the inline knowledge result.thumbnailstringA image URL to the thumbnail image next to the inline knowledge result, if shown.sourcestringThe source of the inline knowledge result.block\_positionstringThe position of inline knowledge result block relative to other SERP features on the Naver SERP page. |
| pagination | object | An object containing details of the pagination section of the page.currentnumberThe current page number, if shown.nextstringThe Naver URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Naver URL to the page. |
Next Steps

* [Naver Search Parameters](/docs/search-api/searches/naver/search)

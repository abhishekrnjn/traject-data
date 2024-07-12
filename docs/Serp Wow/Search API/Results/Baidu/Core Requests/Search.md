Baidu Search Results
--------------------

DESKTOPTABLETMOBILESerpWow parses Baidu search results when the `engine=baidu` request parameter is set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/baidu_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Baidu Search ResultsBelow is an example of how Baidu search results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"organic\_results":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `engine=baidu` requests:

| Property | Type | Description |
| organic\_results | array | An array of Organic Result objects, containing each of the organic results returned. The Organic Result object has the following properties:positionnumberThe position of the organic result on the current page.titlestringThe title of the organic result.linkstringA link to the organic result.domainstringThe domain of the link to the organic result.displayed\_linkstringThe displayed (visual) link shown next to the organic result.urlstringThe destination url for the organic result.snippetstringThe snippet text of the organic result.sitelinksobject| Sitelinks Object | An object containing the sitelinks shown next to the organic search result: |
| --- | --- |
inlinearrayAn array of objects containing title and link properties being the title and link of the inline sitelink. |
| ads | array | An array of Ads objects, containing each of the sponsored ads shown on the Baidu SERP. The Ad object has the following properties:positionnumberThe position of the ad result within the ads on the current page.titlestringThe title text of the ad.tracking\_linkstringThe tracking link that is followed when the Ad is clicked.displayed\_linkstringThe displayed (visual) link shown in the ad.descriptionstringThe descriptive text of the ad.block\_positionstringThe position of ad block this ad belongs to on the Baidu SERP page. Can be set to top or bottom. |
| pagination | object | An object containing details of the pagination section of the page.currentnumberThe current page number, if shown.nextstringThe Baidu URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Baidu URL to the page. |
Next Steps

* [Baidu Search Parameters](/docs/search-api/searches/baidu/search)

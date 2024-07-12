Naver News Results
------------------

DESKTOPTABLETMOBILESerpWow parses Naver News results when the `engine=naver` and `search_type=news` request parameters are set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/naver_news.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Naver News ResultsBelow is an example of how Naver News results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"news\_results":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `engine=naver` and `search_type=news` requests:

| Property | Type | Description |
| news\_results | array | An array of News Result objects, containing each of the news results returned. The News Result object has the following properties:positionnumberThe position of the news result on the current page.titlestringThe title of the news result.linkstringA link to the news result.domainstringThe domain of the link to the news result.sourcestringThe source / publication name of the news result.datestringThe raw date, if shown, of the news result.snippetstringThe snippet text of the news result.thumbnailstringAn image URL to the thumbnail image of the news result, if shown. |
| pagination | object | An object containing details of the pagination section of the page.currentnumberThe current page number, if shown.nextstringThe Naver URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Naver URL to the page. |
Next Steps

* [Naver News Parameters](/docs/search-api/searches/naver/news)

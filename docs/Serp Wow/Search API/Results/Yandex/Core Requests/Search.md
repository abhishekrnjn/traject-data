Yandex Search Results
---------------------

DESKTOPTABLETMOBILESerpWow parses Yandex search results when the `engine=yandex` request parameter is set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/yandex_search.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Yandex Search ResultsBelow is an example of how Yandex search results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"ads":[...]"organic\_results":[...]"local\_results":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `engine=yandex` requests:

| Property | Type | Description |
| organic\_results | array | An array of Organic Result objects, containing each of the organic results returned. The Organic Result object has the following properties:positionnumberThe position of the organic result on the current page.titlestringThe title of the organic result.linkstringA link to the organic result.domainstringThe domain of the link to the organic result.displayed\_linkstringThe displayed (visual) link shown next to the organic result.snippetstringThe snippet text of the organic result. |
| ads | array | An array of Ads objects, containing each of the sponsored ads shown on the Yandex SERP. The Ad object has the following properties:positionnumberThe position of the ad result within the ads on the current page.titlestringThe title text of the ad.tracking\_linkstringThe tracking link that is followed when the Ad is clicked.displayed\_linkstringThe displayed (visual) link shown in the ad.descriptionstringThe descriptive text of the ad.domainstringThe domain of the website behind the ad (extracted from the displayed\_link).block\_positionstringThe position of ad block this ad belongs to on the Yandex SERP page. Can be set to top or bottom. |
| local\_results | array | An array of Local Result objects containing details of the local results shown under the local map on the Yandex SERP page.positionnumberThe position of the local result in the local\_results array.titlestringThe title of the local result, typically the business name.linkstringA link to the local result business website, if shown.logostringAn image URL link to the logo, if shown.thumbnailstringAn image URL link to the thumbnail, if shown.ratingnumberThe customer rating of the local result, out of 5, if shown.reviewsnumberThe number of customers reviews the local result has received.opening\_hoursstringAn opening hours of the local result, if shown. |
| pagination | object | An object containing details of the pagination section of the page.currentnumberThe current page number, if shown.nextstringThe Yandex URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Yandex URL to the page. |
Next Steps

* [Yandex Search Parameters](/docs/search-api/searches/yandex/search)

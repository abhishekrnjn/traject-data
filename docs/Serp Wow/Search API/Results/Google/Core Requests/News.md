Google News Results
-------------------

DESKTOPTABLETMOBILESerpWow parses the Google news search results the`news_results`array in the JSON output when the `search_type=news` search parameter is set.

If you wish to exclude news results where Google have modified the original query set `exclude_if_modified=true` in your request parameters.

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_news.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google News ResultsBelow is an example of how Google News results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"top\_stories":[...]"news\_results":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `search_type=news` requests:

| Property | Type | Description |
| news\_results | array | An array of News Result objects, containing each of the news results returned. The News Result object has the following properties:positionnumberThe position of the news result on the current page.titlestringThe title of the news result.linkstringA link to the news result.domainstringThe domain of the link to the news result.sourcestringThe source / publication name of the news result.datestringThe raw date, if shown, of the news result.date\_utcstringThe parsed date, in ISO 8601 format, of the news result. Note that date parsing relies on the API being able to successfully parse the date and isn't guaranteed in all locales.snippetstringThe snippet text of the news result.thumbnailstringThe thumbnail image of the news result, either returned as a URL to the image, or as a Base64-encoded image string. |
| top\_stories | array | An array of Top Story objects representing the "top stories" horizontally-scrolling carousel section of the news result page, if shown. The Top Story object has the following properties:titlestringThe title of the top story result.linkstringA link to the top story result.visible\_initiallybooleantrue if the top story is visible on page load, false if the top story requires a horizontal scroll of the Top Stories carousel for it to come in to view.sourcestringThe source / publication name of the top story.datestringThe raw date, if shown, of the news result.date\_utcstringThe parsed date, in ISO 8601 format, of the news result. Note that date parsing relies on the API being able to successfully parse the date and isn't guaranteed in all locales.thumbnailstringThe thumbnail image of the top story result, either returned as a URL to the image, or as a Base64-encoded image string.videobooleantrue when the top story is video format and false when not.livebooleantrue when the top story is live video and false when not.block\_positionnumberThe position of the top story carousel, relative to other page features shown. |
| pagination | object | An object containing details of the pagination section of the page. Details are provided as Google links and API links (to make sending paginated requests easier):currentnumberThe current page number, if shown.nextstringThe Google URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Google URL to the page.api\_paginationobjectAn object containing API links to request the next pages of results. Provided as a convenience to allow you to run subsequent requests for additional pages. Contains a next and other\_pages property. |
Next Steps

* [Google News Parameters](/docs/search-api/searches/google/news)

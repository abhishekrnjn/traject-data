Yahoo News Results
------------------

DESKTOPTABLETMOBILESerpWow parses Yahoo News results when the `engine=yahoo` and `search_type=news` request parameters are set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/yahoo_news.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Yahoo News ResultsBelow is an example of how Yahoo News results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"news\_results":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `engine=yahoo` and `search_type=news` requests:

| Property | Type | Description |
| news\_results | array | An array of News Result objects, containing each of the news results returned. The News Result object has the following properties:positionnumberThe position of the news result on the current page.titlestringThe title of the news result.linkstringA link to the news result.domainstringThe domain of the link to the news result.sourcestringThe source / publication name of the news result.datestringThe raw date, if shown, of the news result.date\_utcstringThe parsed date, in ISO 8601 format, of the news result. Note that date parsing relies on the API being able to successfully parse the date and isn't guaranteed in all locales.snippetstringThe snippet text of the news result. |
| pagination | object | An object containing details of the pagination section of the page.currentnumberThe current page number, if shown.nextstringThe Yahoo URL of the next page of results.other\_pagesobjectAn object containing details of the other pages shown on the results page. The object is keyed by the other page number, with the value being the Yahoo URL to the page. |
Next Steps

* [Yahoo News Parameters](/docs/search-api/searches/yahoo/news)

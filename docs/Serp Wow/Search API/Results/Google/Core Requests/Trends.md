Google Trends Results
---------------------

DESKTOPTABLETMOBILESerpWow parses Google Trends results into the `trends_interest_over_time`, `trends_interest_by_subregion`, `related_queries` and `related_topics` properties in the JSON output when the `search_type=trends` search parameter is set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_trends.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Trends ResultsBelow is an example of how the Google Trends results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"trends\_interest\_over\_time":{...}"trends\_interest\_by\_subregion":[0 - 100][100 - 200][200 - 250]"related\_queries":[...]"related\_topics":[...]}Copy### 

SerpWow returns the following properties for `search_type=trends` requests:

| Property | Type | Description |
| trends\_interest\_over\_time | object | dataarray| Data Array | An array of objects for each date-point in the selected date range, at the selected date granularity, showing the interest values for each keyword specified in the q parameter. Each object in the array has the following properties: |
| --- | --- |
date\_utcstringThe parsed date, in ISO 8601 format, of the start date of the time period to which data relates to.date\_formattedstringThe visual date displayed shown to the user on the Google Trends site.valuesarrayAn array of objects, one for each of the keywords entered in the q request parameter. The objects in the values array contain the following properties: keyword, has\_value, value and value\_formatted. |
| trends\_interest\_by\_subregion | array | An array containing interest values for each of the keywords specified in the q request parameter. The resolution of the data shown in the SADASD array is determined by the value of the trends\_resolution request parameter (which can be set to country, city, dma or region). Each object in the array contains the following properties.namestringContains the name of the subregion.valuesarrayAn array of values detailing the numeric interest in the given subregion. Each object in the array contains value, value\_formatted (a text-formatted version of the value property), keyword and has\_value properties.geostringApplies when trends\_resolution=country and contains the trends\_geo value of the country. Can be used in the trends\_geo request parameter. |
| related\_queries | array | An array containing related queries. An entry is placed into the related\_queries array for each of the keywords specified in the q request parameter. Each entry in the related\_queries array contains the following properties.keywordstringThe keyword this related queries object relates to.top\_queriesarrayAn array of "top" related queries. Each object in the array contains value, value\_formatted (a text-formatted version of the value property), query, position and link properties.rising\_queriesarrayAn array of "rising" related queries. Each object in the array contains value, value\_formatted (a text-formatted version of the value property), query, position and link properties. |
| related\_topics | array | An array containing related topics. An entry is placed into the related\_topics array for each of the keywords specified in the q request parameter. Each entry in the related\_topics array contains the following properties.keywordstringThe keyword this related topic object relates to.top\_topicsarrayAn array of "top" related topics. Each object in the array contains value, value\_formatted (a text-formatted version of the value property), query, position and link properties.rising\_topicsarrayAn array of "rising" related topics. Each object in the array contains value, value\_formatted (a text-formatted version of the value property), topic\_title, topic\_type, topic\_id, position and link properties. |
Next Steps

* [Google Trends Parameters](/docs/search-api/searches/google/trends)

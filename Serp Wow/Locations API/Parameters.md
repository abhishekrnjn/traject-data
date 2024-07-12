Parameters
----------

GET`/locations`The following parameters can be used to refine the results from the Locations API.

| Parameter | Required | Description |
| --- | --- | --- |
| api\_key | required | The API key for your account. |
| q | optional | The query to use to search for locations, i.e. new york or mumbai. |
| id | optional | Theidof a specific location (location ids are returned with all results from the Locations API). |
| parent\_id | optional | Limits the search to child locations of the givenparent\_id. Useful for retrieving all sub-locations of a given location (all cities within a country, for example). |
| type | optional | Limits the results to a specific type of location. Valid values arecity,country,county,dma\_region,municipality,neighborhood,state,postal\_codeorprovince. Multiple location types should be presented as a comma seperated list (i.e.type=state,cityto include Location results that are of type stateorcity). |
| country\_code | optional | Limits the results to locations in specific countries. See supported countries for a full list of all supported values. Multiple countries should be presented as a comma seperated list (i.e.country\_code=de,fr,usfor Germany, France and the United States). |
| limit | optional | Limits the number of search results returned per page. Defaults to10. The maximum number of location results returned per page is100. Use in conjunction with the the page parameter to implement pagination. |
| page | optional | Specifies the page of results to retrieve from 0 (first page) to a maximum page number of 100 (SerpWow does not support paging beyond the 100th page). Defaults to0. Use in conjunction with the limit parameter to limit the number of results returned per page. |

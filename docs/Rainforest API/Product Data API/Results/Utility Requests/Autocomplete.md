Autocomplete Results
--------------------

When making a request with the `type` [parameter](/docs/product-data-api/parameters/autocomplete) set to `type=autocomplete` Rainforest API will return autocomplete suggestions for the search term specified in the `search_term` parameter, on the Amazon domain specified in the `amazon_domain` parameter.

![]()Autocomplete SuggestionsAn example of the JSON object returned from an Autocomplete request is shown below:

{"request\_info":{...}"request\_metadata":{...}"request\_parameters":{...}"autocomplete\_results":[...]}CopyRainforest API returns the following properties for Autocomplete requests:

PropertyTypeDescriptionautocomplete\_resultsarray**Autocomplete Results Array**The autocomplete results array contains details of each of the autocomplete suggestions returned from the query.suggestionstringThe text of the autocomplete suggestion.typestringThe type of the suggestion.spelling\_correctedbooleanTrue/false depending on whether the suggestion is a result of correcting the spelling of the original `search_term`.Next Steps

* [Autocomplete Parameters](/docs/product-data-api/parameters/autocomplete)

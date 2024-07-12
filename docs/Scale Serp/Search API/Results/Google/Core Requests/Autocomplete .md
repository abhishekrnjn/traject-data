Google Autocomplete Results
---------------------------

DESKTOPTABLETMOBILEScale SERP parses the Google autocomplete results from the search bar into the`autocomplete_results`array in the JSON output when the `search_type=autocomplete` search parameter is set.

![](https://apiimages.imgix.net/scaleserp/images/png/docs/autocomplete.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Autocomplete ResultsBelow is an example of how the`autocomplete_results`array is represented in the Scale SERP result JSON:

{"autocomplete\_results":[...]}Copy### 

Scale SERP returns the following properties for `search_type=autocomplete` requests:

PropertyTypeDescriptionautocomplete\_resultsarrayAn array of AutoComplete Result objects, containing each of the autocomplete results returned. The Autocomplete Result object has the following properties:  
valuestringThe autocomplete suggested text.value\_formattedstringThe HTML-formatted autocomplete suggested text. Typically highlighting the most important work or phrase in the autocomplete suggestion.highlighted\_termsarrayA array of strings representing the bold-highlighted terms in the autocomplete suggestions.Next Steps

* [Google Autocomplete Parameters](/docs/search-api/searches/google/autocomplete)

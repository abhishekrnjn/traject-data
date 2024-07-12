Google Reverse Image Results
----------------------------

DESKTOPTABLETMOBILESerpWow parses the Google Reverse Image search results the `visual_matches` property in the JSON output when the `search_type=reverse_image_search` search parameter is set.

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_reverse_image_new.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Reverse Image ResultsBelow is an example of how Reverse Image results are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"visual\_matches":[...]}Copy### 

SerpWow returns the following properties for `search_type=reverse_image_search` requests:

| Property | Type | Description |
| visual\_matches | array | An array of visual matches.positionnumberThe position of the visual match ordered left to right.linkstringA link to the page hosting the visual match.domainstringThe domain of the link to the page hosting the visual match.imagestringA Base64 thumbnail image of the visual match.titlestringThe title of webpage where image is hosted |
Next Steps

* [Google Reverse Image Parameters](/docs/search-api/searches/google/reverse-image)

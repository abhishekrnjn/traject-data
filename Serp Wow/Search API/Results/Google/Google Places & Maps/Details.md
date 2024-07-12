Google Place Details Results
----------------------------

DESKTOPTABLETMOBILESerpWow parses Place Details into the `place_details` object in the JSON output when the `search_type=place_details` request parameter is set and the `data_id` request parameter is set to a valid `data_id` as-returned by a `search_type=places` [Places requests](/docs/search-api/searches/google/places).

![]()Google Place Details ResultsBelow is an example of how the Place Details are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"place\_details":{...}}Copy### 

SerpWow returns the following properties for `search_type=place_details` requests:

| Property | Type | Description |
| place\_details | object | The Place Details object has the following properties:titlenumberThe title of the place.typestringA type of the place.categorystringA category of the place.websitestringA website URL of the place, if shown.descriptionstringA description of the place.addressstringA address of the place.phonestringA phone number of the place.ratingnumberThe customer rating of the place, out of 5.reviewsnumberThe number of customer reviews the place has received.unclaimedbooleanSetto true when the Google My Business listing shown in the place result has not been "claimed" by the owner.hoursarrayAn array of objects representing the opening hours of the Place. Each object contains a name and value string property.opening\_hoursarrayAn array of objects representing the opening hours of the Place in a more extensively parsed form.people\_also\_search\_forarrayAn array of objects from the 'people also search for' section. Each object contains a name and category string property.menuarrayAn array of objects representing the available menus of the Place. Each object contains a text and link string property.reservationsarrayAn array of objects representing the reservation links for Place. Each object contains a text and link string property.orderarrayAn array of objects representing the ordering links for Place. Each object contains a text and link string property.order\_foodarrayAn array of objects representing the specific food-ordering links for Place. Each object contains a text and link string property.known\_attributesarray| Known Attributes Array | An array of objects containing the known attributes shown on the place details page. |
| --- | --- |
attributestringThe attribute name of the known attribute.valueobjectAn object containing a name and optional link property showing the value of the known attribute.namestringThe name of the known attribute.linkstringThe link of the known attribute.valuestringThe value of the known attribute. |
Next Steps

* [Google Place Details Parameters](/docs/search-api/searches/google/place-details)

Google Place Reviews Results
----------------------------

DESKTOPTABLETMOBILESerpWow parses the Place Reviews results the `place_reviews_results` array in the JSON output when the `search_type=place_reviews` request parameter is set and the `data_id` request parameter is set to a valid `data_id` as-returned by a `search_type=places` [Places requests](/docs/search-api/searches/google/places).

![](https://apiimages.imgix.net/serpwow/images/png/docs/google_place_reviews.png?auto=format&ixlib=react-9.5.1-beta.1&w=600)Google Place Reviews ResultsBelow is an example of how the Place Reviews are represented in the SerpWow result JSON:

{"request\_info":{...}"search\_metadata":{...}"search\_parameters":{...}"search\_information":{...}"place\_reviews\_results":[...]"place\_info":{...}"topics":[...]"pagination":{...}}Copy### 

SerpWow returns the following properties for `search_type=place_reviews` requests:

| Property | Type | Description |
| place\_reviews\_results | array | An array of Place Review result objects, containing each of the Place Review results returned. The Place Review Result object has the following properties:positionnumberThe position of the review on the current page of reviews.sourcestringThe user name of the user who left the review.source\_linkstringA link to the profile page of the user who left the review.source\_imagestringAn image URL to the profile image of the user who left the review.source\_idstringThe ID of the user who left the review.source\_review\_countnumberThe total number of reviews, of any Place, left by this user.bodystringThe body text of the review.body\_htmlstringThe HTML of the review body, useful if you wish to preserve HTML formatting.idstringThe ID of the review.ratingnumberThe rating given to the Place by the review author, out of 5.imagesarrayAn array of image URL strings for each of the user-supplied images left by the reviewer, if shown.datestringThe raw date of the review.date\_utcstringThe parsed date, in ISO 8601 format, of the review. Note that date parsing relies on the API being able to successfully parse the date and isn't guaranteed in all locales. |
| place\_info | object | titlestringThe title of the Place.addressstringThe address of the Place.ratingnumberThe customer rating of the Place, out of 5.reviewsnumberThe number of customer reviews this Place as received. |
| topics | array | An array of Topic objects. You can take the id of a topic and pass it in to the topic\_id parameter of a subsequent search\_type=place\_reviews request to retrieve place reviews related to that topic.keywordstringThe topic keyword.idstringThe ID of the topic. Can be passed in to the topic\_id parameter of a subsequent search\_type=place\_reviews request to retrieve place reviews related to that topic.mentionsnumberThe number of times the topic is mention in this Places' reviews. Is a relative measure of how much reviewers discuss this topic. |
| pagination | object | next\_page\_tokenstringA token that can be passed in a subsequent search\_type=place\_reviews request to provide the next page of Place Reviews results.Note Place Review results do not contain a traditional pagination section where a specific page of results is uniquely addressable. Instead the next\_page\_token can be passed in to the next\_page\_token request parameter to retrieve the next page of place reviews results. |
Next Steps

* [Google Place Reviews Parameters](/docs/search-api/searches/google/place-reviews)

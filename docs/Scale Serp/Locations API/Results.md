Results
-------

The Locations API returns structured JSON. The`locations`array contains the Scale SERP supported locations that match the given [parameters](/docs/locations-api/parameters).



**Searching based on a Location**  
You should supply the value from the`full_name`property returned by the Locations API to the`location`parameter of the [Search API](/docs/search-api) to get localized search results from that location.

**Reach**  
The`reach`property returned by the Locations API gives an indication of the population size in the given location. You can use it to disambiguate similarly named locations.An example result from the Locations API is shown below.


```
{
  "request_info": {
    "success": true
  },
  "locations_total": 232,
  "page": 0,
  "limit": 10,
  "locations": [
    {
      "id": 9041106,
      "name": "Greater London",
      "type": "County",
      "full_name": "Greater London,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 20800000
    },
    {
      "id": 1006886,
      "name": "London",
      "type": "City",
      "full_name": "London,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 19900000
    },
    {
      "id": 9041110,
      "name": "City of London",
      "type": "County",
      "full_name": "City of London,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 19900000
    },
    {
      "id": 1002316,
      "name": "London Borough of Lambeth",
      "type": "Municipality",
      "full_name": "London Borough of Lambeth,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 983000
    },
    {
      "id": 9057243,
      "name": "New London County",
      "type": "County",
      "full_name": "New London County,Connecticut,United States",
      "parent_id": 21139,
      "country_code": "US",
      "reach": 434000
    },
    {
      "id": 1002325,
      "name": "London",
      "type": "City",
      "full_name": "London,Ontario,Canada",
      "parent_id": 20121,
      "country_code": "CA",
      "reach": 418000
    },
    {
      "id": 1007284,
      "name": "Londonderry",
      "type": "City",
      "full_name": "Londonderry,Northern Ireland,United Kingdom",
      "parent_id": 20341,
      "country_code": "GB",
      "reach": 192000
    },
    {
      "id": 9041230,
      "name": "London Stansted Airport",
      "type": "Airport",
      "full_name": "London Stansted Airport,England,United Kingdom",
      "parent_id": 20339,
      "country_code": "GB",
      "reach": 153000
    },
    {
      "id": 1017821,
      "name": "London",
      "type": "City",
      "full_name": "London,Kentucky,United States",
      "parent_id": 21150,
      "country_code": "US",
      "reach": 144000
    },
    {
      "id": 1014779,
      "name": "New London",
      "type": "City",
      "full_name": "New London,Connecticut,United States",
      "parent_id": 21139,
      "country_code": "US",
      "reach": 136000
    }
  ]
}
```
Copy
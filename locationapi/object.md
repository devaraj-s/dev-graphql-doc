# Objects

## LocationAPI
Graph based API to get Location or Location.  <br />

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `location` | [Location](object#location) | Navigate location graph via this query, you will use this if you have access to location code otherwise use search query. Returns an Location object.  |
| `locationbyIds` | [[Location]](object#location) | Navigate location graph via this query, you will use this if you have access to location code otherwise use search query. Returns an collection Location object.  |
| `search` | [[Location]](object#location) | Lookup location by name, title or any other information you know. Returns the matching location objects as an array.  |
| `searchfilter` | [[Location]](object#location) | Lookup location by name, title or any other information you know. Returns the matching location objects as an array.  |
| `locations` | [[Location]](object#location) | Returns all location which exists sorted in ascending order by officeCode  |
| `hotels` | [[Hotel]](object#hotel) | Lookup for hotels in given location. Returns hotel in the location in a array  |
| `airports` | [[Airport]](object#airport) | Lookup for airports in given location. Returns airports in the location in a array  |
| `searchByAddress` | [[Location]](object#location) | Search for the given text and return collection of location data using  third party api.This locations are not available in location master  |
| `LocationAPIProfileQuery_Realtimecustomreport` | [[String]](scalar#string) | LocationAPI real time custom report. <br /> <iframe src="https://www.site24x7.eu/public/dashboard/I6RSF5T1vs2VmjfvcW_EdbuuY2099IWqSJzovxoDudGlBW5Tkx55s7bPHfqIzxvLEOtJnC8lr8dQtZG5e-rGONE9Ue6GjDDiVh8LVWTUuavrq3xlVKIiynzbPbiIhati" scrolling="yes" align="center" height="200" width="800" border="0" frameborder="0"></iframe>  <br />  |
| `LocationAPIResponseTime_Oneweektimelinedata` | [[String]](scalar#string) | <iframe src="https://app.datadoghq.com/graph/embed?token=604d6baee98a8207f465840f9eeef3847bf06fa983bf64be7f6489793fbb61c5&height=200&width=400&legend=true" width="400" height="200" frameborder="0"></iframe>   |

## Location
Location Type - object for the office location

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Unique office code  |
| `name` | [String](scalar#string) | Office name  |
| `regionId` | [String](scalar#string) | Unique region id of the office  |
| `street` | [String](scalar#string) | Street where office is located  |
| `street2` | [String](scalar#string) | Street where office is located  |
| `street3` | [String](scalar#string) | Street where office is located  |
| `city` | [String](scalar#string) | City of office  |
| `state` | [String](scalar#string) | State of Office  |
| `zipCode` | [String](scalar#string) | Zip-code of office  |
| `country` | [String](scalar#string) | Country of office  |
| `countryCode` | [String](scalar#string) | Country code of office  |
| `geoLocation` | [GeoLocation](object#geolocation) | Geolocation has latitude and longitude  |
| `phone` | [String](scalar#string) | Phone number of office  |
| `imageUrl` | [String](scalar#string) | Link to an office image  |
| `contentLinks` | [[ContentType]](object#contenttype) | Contents inside the office location  |
| `timezone` | [String](scalar#string) | Time zone of the location  |
| `weather` | [Weather](object#weather) | current weather for the location  |
| `locationType` | [String](scalar#string) | Location type  |

## GeoLocation
GeoLocation Type - object for latitude and longitude

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `lat` | [String](scalar#string) | Latitude of a geo location  |
| `lon` | [String](scalar#string) | Longitude of a geo location  |

## ContentType
Object representation for the ContentLink

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](scalar#string) | Name of the content  |
| `link` | [String](scalar#string) | Link to the content  |
| `image` | [String](scalar#string) | Icon name for the content  |

## Weather
Weather Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `icon` | [String](scalar#string) | Weather icon to be used  |
| `description` | [String](scalar#string) | Weather description of the description  |
| `temperature` | [[WeatherUnit]](object#weatherunit) | Temperature in both celcius and farenheit  |

## WeatherUnit
Weather Unit Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `type` | [String](scalar#string) | Unit Type- Celcius or Farenheit  |
| `value` | [Float](scalar#float) | Current temperature  |

## Hotel
Hotel Type - object for the Hotel location

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Unique Hotel code  |
| `name` | [String](scalar#string) | Hotel name  |
| `street` | [String](scalar#string) | Street where Hotel is located  |
| `city` | [String](scalar#string) | City of Hotel  |
| `state` | [String](scalar#string) | State of Hotel  |
| `zipCode` | [String](scalar#string) | Zip-code of Hotel  |
| `country` | [String](scalar#string) | Country of Hotel  |
| `address` | [String](scalar#string) | Country code of Hotel  |
| `geoLocation` | [GeoLocation](object#geolocation) | Geolocation has latitude and longitude  |
| `phone` | [String](scalar#string) | Phone number of Hotel  |
| `imageUrl` | [String](scalar#string) | Link to an Hotel image  |
| `contentLinks` | [[ContentType]](object#contenttype) | Contents inside the Hotel location  |
| `ratings` | [String](scalar#string) | User ratings for the Hotel  |
| `distance` | [Float](scalar#float) | Distance from the office location  |
| `preferred` | [Boolean](scalar#boolean) | BCG Preferred hotel  |

## Airport
Airport Type - object for the airport location

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Unique airport code  |
| `name` | [String](scalar#string) | Airport name  |
| `street` | [String](scalar#string) | Street where airport is located  |
| `city` | [String](scalar#string) | City of airport  |
| `state` | [String](scalar#string) | State of airport  |
| `zipCode` | [String](scalar#string) | Zip-code of airport  |
| `country` | [String](scalar#string) | Country of airport  |
| `address` | [String](scalar#string) | Country code of airport  |
| `geoLocation` | [GeoLocation](object#geolocation) | Geolocation has latitude and longitude  |
| `phone` | [String](scalar#string) | Phone number of airport  |
| `imageUrl` | [String](scalar#string) | Link to an airport image  |
| `contentLinks` | [[ContentType]](object#contenttype) | Contents inside the airport location  |
| `ratings` | [String](scalar#string) | User ratings for the airport  |
| `distance` | [Float](scalar#float) | Distance from the office location  |

## LocationAPIMutation
GraphQL mutation to update location

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `updateLocation` | [Location](object#location) | Update the location  |
| `addLocation` | [Location](object#location) | Add the location  |
| `markHotelPreferred` | [Hotel](object#hotel) | Mark the hotel as preferred  |

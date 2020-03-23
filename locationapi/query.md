---
layout: default
---
# LocationAPI
Graph based API to get Location or Location.  <br />
**location** (`id`: [String](scalar#string)) : [Location](object#location)

Navigate location graph via this query, you will use this if you have access to location code otherwise use search query. Returns an Location object.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) |  |

**locationbyIds** (`ids`: [[String]](scalar#string)) : [[Location]](object#location)

Navigate location graph via this query, you will use this if you have access to location code otherwise use search query. Returns an collection Location object.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `ids` | [[String]](scalar#string) | Array of location office code |

**search** (`filter`: [String](scalar#string), `filters`: [[String]](scalar#string), `filterType`: [FilterType](enum#filtertype)) : [[Location]](object#location)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `filter` | [String](scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "zipCode=123456" |
| `filters` | [[String]](scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**searchfilter** (`filters`: [[search]](search)) : [[Location]](object#location)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |

**locations** (`regions`: [[RegionType]](enum#regiontype)) : [[Location]](object#location)

Returns all location which exists sorted in ascending order by officeCode

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `regions` | [[RegionType]](enum#regiontype) |  |

**hotels** (`locationId`: [String](scalar#string)) : [[Hotel]](object#hotel)

Lookup for hotels in given location. Returns hotel in the location in a array

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `locationId` | [String](scalar#string) |  |

**airports** (`locationId`: [String](scalar#string)) : [[Airport]](object#airport)

Lookup for airports in given location. Returns airports in the location in a array

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `locationId` | [String](scalar#string) |  |

**searchByAddress** (`text`: [String](scalar#string)) : [[Location]](object#location)

Search for the given text and return collection of location data using  third party api.This locations are not available in location master <br />

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `text` | [String](scalar#string) |  |

**LocationAPICustomOfficesQuery_Realtimecustomreport**  : [[String]](scalar#string)

 <iframe src="https://www.site24x7.eu/public/dashboard/I6RSF5T1vs2VmjfvcW_EdbuuY2099IWqSJzovxoDudGlBW5Tkx55s7bPHfqIzxvLEOtJnC8lr8dQtZG5e-rGONE9Ue6GjDDiVh8LVWTUuavrq3xlVKIiynzbPbiIhati" scrolling="yes" align="center" height="200" width="800" border="0" frameborder="0"></iframe>  <br />

**LocationAPIResponseTime_Oneweektimelinedata**  : [[String]](scalar#string)

<iframe src="https://app.datadoghq.com/graph/embed?token=604d6baee98a8207f465840f9eeef3847bf06fa983bf64be7f6489793fbb61c5&height=200&width=400&legend=true" width="400" height="200" frameborder="0"></iframe> 

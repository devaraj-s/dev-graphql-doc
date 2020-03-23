---
layout: default
---
# PeopleExternalAPI
Graph based API to get External People information. You can use an Employee query if employee id is known or use a Search query to look up an Employee.<br />
**employees** (`ids`: [[String]](scalar#string), `sector`: [String](scalar#string)) : [[Employee]](object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `ids` | [[String]](scalar#string) | Array of employee ids |
| `sector` | [String](scalar#string) | Sector of experts for e.g MPI or TL |

**employee** (`id`: [String](scalar#string), `field`: [String](scalar#string), `dataSet`: [DataSet](enum#dataset), `sector`: [String](scalar#string)) : [Employee](object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Employee Id |
| `field` | [String](scalar#string) |  |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sector` | [String](scalar#string) | Sector of experts for e.g MPI or TL |

**peopleSearch** (`find`: [String](scalar#string), `filter`: [String](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](enum#dataset), `sortBy`: [String](scalar#string), `filters`: [[String]](scalar#string), `filterType`: [FilterType](enum#filtertype), `sector`: [String](scalar#string)) : [Employees](object#employees)

Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](scalar#string) | Value of find should be an Employee name eg : "Lastname Firstname" or vise versa |
| `filter` | [String](scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](enum#filtertype) | Filter type OR/AND/NOT. Default is OR |
| `sector` | [String](scalar#string) | Sector of experts for e.g MPI or TL |

**searchFilter** (`find`: [String](scalar#string), `filters`: [[search]](search), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `sortBy`: [String](scalar#string), `sector`: [String](scalar#string)) : [Employees](object#employees)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](scalar#string) | Text search for e.g "Firstname" or "Lead" |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |
| `sector` | [String](scalar#string) | Sector of experts for e.g MPI or TL |

**jobFunctions** (`sector`: [String](scalar#string)) : [[JobFunction]](object#jobfunction)

Returns list of all distinct job functions

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `sector` | [String](scalar#string) | Sector of experts for e.g MPI or TL |

**practiceAreas** (`sector`: [String](scalar#string)) : [[PracticeArea]](object#practicearea)

Returns list of all practice area objects

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `sector` | [String](scalar#string) | Sector of experts for e.g MPI or TL |

**advancedFilters** (`sector`: [String](scalar#string)) : [AdvancedFilters](object#advancedfilters)

Returns list of available advanced filters <br />

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `sector` | [String](scalar#string) | Sector of experts for e.g MPI or TL |



# PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.
**employees** (`ids`: [[String]](eventsapi/scalar#string), `dataSet`: [DataSet](eventsapi/enum#dataset)) : [[Employee]](eventsapi/object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `ids` | [[String]](eventsapi/scalar#string) | Array of employee ids |
| `dataSet` | [DataSet](eventsapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**employee** (`id`: [String](eventsapi/scalar#string), `field`: [String](eventsapi/scalar#string), `dataSet`: [DataSet](eventsapi/enum#dataset)) : [Employee](eventsapi/object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](eventsapi/scalar#string) | Employee Id |
| `field` | [String](eventsapi/scalar#string) |  |
| `dataSet` | [DataSet](eventsapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

`Deprecated`**search** (`find`: [String](eventsapi/scalar#string), `filter`: [String](eventsapi/scalar#string), `limit`: [Int](eventsapi/scalar#int), `offset`: [Int](eventsapi/scalar#int), `dataSet`: [DataSet](eventsapi/enum#dataset), `sortBy`: [String](eventsapi/scalar#string), `filters`: [[String]](eventsapi/scalar#string), `filterType`: [FilterType](eventsapi/enum#filtertype)) : [[Employee]](eventsapi/object#employee)
*Search has been deprecated, Use peopleSearch() instead*
DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](eventsapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](eventsapi/scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](eventsapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](eventsapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](eventsapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](eventsapi/scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](eventsapi/scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](eventsapi/enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**peopleSearch** (`find`: [String](eventsapi/scalar#string), `filter`: [String](eventsapi/scalar#string), `limit`: [Int](eventsapi/scalar#int), `offset`: [Int](eventsapi/scalar#int), `dataSet`: [DataSet](eventsapi/enum#dataset), `sortBy`: [String](eventsapi/scalar#string), `filters`: [[String]](eventsapi/scalar#string), `filterType`: [FilterType](eventsapi/enum#filtertype)) : [Employees](eventsapi/object#employees)

Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](eventsapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](eventsapi/scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](eventsapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](eventsapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](eventsapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](eventsapi/scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](eventsapi/scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](eventsapi/enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**searchFilter** (`find`: [String](eventsapi/scalar#string), `filters`: [[search]](search), `resultFilters`: [[String]](eventsapi/scalar#string), `limit`: [Int](eventsapi/scalar#int), `offset`: [Int](eventsapi/scalar#int), `dataSet`: [DataSet](eventsapi/enum#dataset), `sortBy`: [String](eventsapi/scalar#string)) : [Employees](eventsapi/object#employees)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](eventsapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |
| `resultFilters` | [[String]](eventsapi/scalar#string) | Possible filters and available result counts |
| `limit` | [Int](eventsapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](eventsapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](eventsapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](eventsapi/scalar#string) | A field name by which the list is suppose to be ordered by |

**jobFunctions** (`dataSet`: [DataSet](eventsapi/enum#dataset)) : [[JobFunction]](eventsapi/object#jobfunction)

Returns list of all distinct job functions

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](eventsapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**practiceAreas**  : [[PracticeArea]](eventsapi/object#practicearea)

Returns list of all practice area objects

**cohorts** (`dataSet`: [DataSet](eventsapi/enum#dataset)) : [[String]](eventsapi/scalar#string)

Returns list of all distinct cohorts

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](eventsapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**preferences** (`employeeId`: [String!](eventsapi/scalar#string), `key`: [String](eventsapi/scalar#string)) : [[OutputPreference]](eventsapi/object#outputpreference)

Returns list of preferences

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String!](eventsapi/scalar#string) | Employee ID for which all preferences needs to be fetched |
| `key` | [String](eventsapi/scalar#string) | preference type for which all preferences needs to be fetched |

**team** (`teamId`: [String](eventsapi/scalar#string)) : [TeamOutput](eventsapi/object#teamoutput)

Return team for given team Id

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `teamId` | [String](eventsapi/scalar#string) | Team Id |

**teams** (`employeeId`: [String!](eventsapi/scalar#string)) : [[TeamOutput]](eventsapi/object#teamoutput)

Returns list of all the teams for an employee

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String!](eventsapi/scalar#string) | Employee ID for which all teams needs to be fetched |

**allTeams**  : [[TeamOutput]](eventsapi/object#teamoutput)

Returns list of all the teams

**entitlements**  : [[String]](eventsapi/scalar#string)

Returns list of all groups of an employee

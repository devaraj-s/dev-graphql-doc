# PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.
**employees** (`ids`: [[String]](peopleapi/scalar#string), `dataSet`: [DataSet](peopleapi/enum#dataset)) : [[Employee]](peopleapi/object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `ids` | [[String]](peopleapi/scalar#string) | Array of employee ids |
| `dataSet` | [DataSet](peopleapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**employee** (`id`: [String](peopleapi/scalar#string), `field`: [String](peopleapi/scalar#string), `dataSet`: [DataSet](peopleapi/enum#dataset)) : [Employee](peopleapi/object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](peopleapi/scalar#string) | Employee Id |
| `field` | [String](peopleapi/scalar#string) |  |
| `dataSet` | [DataSet](peopleapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

`Deprecated`**search** (`find`: [String](peopleapi/scalar#string), `filter`: [String](peopleapi/scalar#string), `limit`: [Int](peopleapi/scalar#int), `offset`: [Int](peopleapi/scalar#int), `dataSet`: [DataSet](peopleapi/enum#dataset), `sortBy`: [String](peopleapi/scalar#string), `filters`: [[String]](peopleapi/scalar#string), `filterType`: [FilterType](peopleapi/enum#filtertype)) : [[Employee]](peopleapi/object#employee)
*Search has been deprecated, Use peopleSearch() instead*
DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](peopleapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](peopleapi/scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](peopleapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](peopleapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](peopleapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](peopleapi/scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](peopleapi/scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](peopleapi/enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**peopleSearch** (`find`: [String](peopleapi/scalar#string), `filter`: [String](peopleapi/scalar#string), `limit`: [Int](peopleapi/scalar#int), `offset`: [Int](peopleapi/scalar#int), `dataSet`: [DataSet](peopleapi/enum#dataset), `sortBy`: [String](peopleapi/scalar#string), `filters`: [[String]](peopleapi/scalar#string), `filterType`: [FilterType](peopleapi/enum#filtertype)) : [Employees](peopleapi/object#employees)

Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](peopleapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](peopleapi/scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](peopleapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](peopleapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](peopleapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](peopleapi/scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](peopleapi/scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](peopleapi/enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**searchFilter** (`find`: [String](peopleapi/scalar#string), `filters`: [[search]](search), `resultFilters`: [[String]](peopleapi/scalar#string), `limit`: [Int](peopleapi/scalar#int), `offset`: [Int](peopleapi/scalar#int), `dataSet`: [DataSet](peopleapi/enum#dataset), `sortBy`: [String](peopleapi/scalar#string)) : [Employees](peopleapi/object#employees)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](peopleapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |
| `resultFilters` | [[String]](peopleapi/scalar#string) | Possible filters and available result counts |
| `limit` | [Int](peopleapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](peopleapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](peopleapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](peopleapi/scalar#string) | A field name by which the list is suppose to be ordered by |

**jobFunctions** (`dataSet`: [DataSet](peopleapi/enum#dataset)) : [[JobFunction]](peopleapi/object#jobfunction)

Returns list of all distinct job functions

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](peopleapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**practiceAreas**  : [[PracticeArea]](peopleapi/object#practicearea)

Returns list of all practice area objects

**cohorts** (`dataSet`: [DataSet](peopleapi/enum#dataset)) : [[String]](peopleapi/scalar#string)

Returns list of all distinct cohorts

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](peopleapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**preferences** (`employeeId`: [String!](peopleapi/scalar#string), `key`: [String](peopleapi/scalar#string)) : [[OutputPreference]](peopleapi/object#outputpreference)

Returns list of preferences

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String!](peopleapi/scalar#string) | Employee ID for which all preferences needs to be fetched |
| `key` | [String](peopleapi/scalar#string) | preference type for which all preferences needs to be fetched |

**team** (`teamId`: [String](peopleapi/scalar#string)) : [TeamOutput](peopleapi/object#teamoutput)

Return team for given team Id

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `teamId` | [String](peopleapi/scalar#string) | Team Id |

**teams** (`employeeId`: [String!](peopleapi/scalar#string)) : [[TeamOutput]](peopleapi/object#teamoutput)

Returns list of all the teams for an employee

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String!](peopleapi/scalar#string) | Employee ID for which all teams needs to be fetched |

**allTeams**  : [[TeamOutput]](peopleapi/object#teamoutput)

Returns list of all the teams

**entitlements**  : [[String]](peopleapi/scalar#string)

Returns list of all groups of an employee

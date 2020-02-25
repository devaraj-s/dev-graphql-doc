# PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.
**employees** (`ids`: [[String]](locationapi/scalar#string), `dataSet`: [DataSet](locationapi/enum#dataset)) : [[Employee]](locationapi/object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `ids` | [[String]](locationapi/scalar#string) | Array of employee ids |
| `dataSet` | [DataSet](locationapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**employee** (`id`: [String](locationapi/scalar#string), `field`: [String](locationapi/scalar#string), `dataSet`: [DataSet](locationapi/enum#dataset)) : [Employee](locationapi/object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](locationapi/scalar#string) | Employee Id |
| `field` | [String](locationapi/scalar#string) |  |
| `dataSet` | [DataSet](locationapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

`Deprecated`**search** (`find`: [String](locationapi/scalar#string), `filter`: [String](locationapi/scalar#string), `limit`: [Int](locationapi/scalar#int), `offset`: [Int](locationapi/scalar#int), `dataSet`: [DataSet](locationapi/enum#dataset), `sortBy`: [String](locationapi/scalar#string), `filters`: [[String]](locationapi/scalar#string), `filterType`: [FilterType](locationapi/enum#filtertype)) : [[Employee]](locationapi/object#employee)
*Search has been deprecated, Use peopleSearch() instead*
DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](locationapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](locationapi/scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](locationapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](locationapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](locationapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](locationapi/scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](locationapi/scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](locationapi/enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**peopleSearch** (`find`: [String](locationapi/scalar#string), `filter`: [String](locationapi/scalar#string), `limit`: [Int](locationapi/scalar#int), `offset`: [Int](locationapi/scalar#int), `dataSet`: [DataSet](locationapi/enum#dataset), `sortBy`: [String](locationapi/scalar#string), `filters`: [[String]](locationapi/scalar#string), `filterType`: [FilterType](locationapi/enum#filtertype)) : [Employees](locationapi/object#employees)

Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](locationapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](locationapi/scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](locationapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](locationapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](locationapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](locationapi/scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](locationapi/scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](locationapi/enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**searchFilter** (`find`: [String](locationapi/scalar#string), `filters`: [[search]](search), `resultFilters`: [[String]](locationapi/scalar#string), `limit`: [Int](locationapi/scalar#int), `offset`: [Int](locationapi/scalar#int), `dataSet`: [DataSet](locationapi/enum#dataset), `sortBy`: [String](locationapi/scalar#string)) : [Employees](locationapi/object#employees)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](locationapi/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |
| `resultFilters` | [[String]](locationapi/scalar#string) | Possible filters and available result counts |
| `limit` | [Int](locationapi/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](locationapi/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](locationapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](locationapi/scalar#string) | A field name by which the list is suppose to be ordered by |

**jobFunctions** (`dataSet`: [DataSet](locationapi/enum#dataset)) : [[JobFunction]](locationapi/object#jobfunction)

Returns list of all distinct job functions

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](locationapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**practiceAreas**  : [[PracticeArea]](locationapi/object#practicearea)

Returns list of all practice area objects

**cohorts** (`dataSet`: [DataSet](locationapi/enum#dataset)) : [[String]](locationapi/scalar#string)

Returns list of all distinct cohorts

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](locationapi/enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**preferences** (`employeeId`: [String!](locationapi/scalar#string), `key`: [String](locationapi/scalar#string)) : [[OutputPreference]](locationapi/object#outputpreference)

Returns list of preferences

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String!](locationapi/scalar#string) | Employee ID for which all preferences needs to be fetched |
| `key` | [String](locationapi/scalar#string) | preference type for which all preferences needs to be fetched |

**team** (`teamId`: [String](locationapi/scalar#string)) : [TeamOutput](locationapi/object#teamoutput)

Return team for given team Id

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `teamId` | [String](locationapi/scalar#string) | Team Id |

**teams** (`employeeId`: [String!](locationapi/scalar#string)) : [[TeamOutput]](locationapi/object#teamoutput)

Returns list of all the teams for an employee

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String!](locationapi/scalar#string) | Employee ID for which all teams needs to be fetched |

**allTeams**  : [[TeamOutput]](locationapi/object#teamoutput)

Returns list of all the teams

**entitlements**  : [[String]](locationapi/scalar#string)

Returns list of all groups of an employee

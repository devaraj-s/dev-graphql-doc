# PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.<br /><br />**CodeSamples:** [[Code]](peopleapi_code#Code) <br /><br />
**employees** (`ids`: [[String]](scalar#string), `dataSet`: [DataSet](enum#dataset)) : [[Employee]](object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `ids` | [[String]](scalar#string) | Array of employee ids |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**employee** (`id`: [String](scalar#string), `field`: [String](scalar#string), `dataSet`: [DataSet](enum#dataset)) : [Employee](object#employee)

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Employee Id |
| `field` | [String](scalar#string) |  |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

`Deprecated`**search** (`find`: [String](scalar#string), `filter`: [String](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](enum#dataset), `sortBy`: [String](scalar#string), `filters`: [[String]](scalar#string), `filterType`: [FilterType](enum#filtertype)) : [[Employee]](object#employee)
*Search has been deprecated, Use peopleSearch() instead*
DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**peopleSearch** (`find`: [String](scalar#string), `filter`: [String](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](enum#dataset), `sortBy`: [String](scalar#string), `filters`: [[String]](scalar#string), `filterType`: [FilterType](enum#filtertype)) : [Employees](object#employees)

Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by. |
| `filters` | [[String]](scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**searchFilter** (`find`: [String](scalar#string), `filters`: [[search]](search), `resultFilters`: [[String]](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](enum#dataset), `sortBy`: [[String]](scalar#string), `sortOrder`: [SortOrder](enum#sortorder)) : [Employees](object#employees)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](scalar#string) | Find employee by name or designation i.e. search on fields: "Lastname, Firstname, Title, PracticeArea Topic, JobFunction, GlobalTitle" |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |
| `resultFilters` | [[String]](scalar#string) | Possible filters and available result counts |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [[String]](scalar#string) | A field name by which the list is suppose to be ordered by. |
| `sortOrder` | [SortOrder](enum#sortorder) | Order of sorting. |

**jobFunctions** (`dataSet`: [DataSet](enum#dataset)) : [[JobFunction]](object#jobfunction)

Returns list of all distinct job functions

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**practiceAreas**  : [[PracticeArea]](object#practicearea)

Returns list of all practice area objects

**cohorts** (`dataSet`: [DataSet](enum#dataset)) : [[String]](scalar#string)

Returns list of all distinct cohorts

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**preferences** (`employeeId`: [String!](scalar#string), `key`: [String](scalar#string)) : [[OutputPreference]](object#outputpreference)

Returns list of preferences

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String!](scalar#string) | Employee ID for which all preferences needs to be fetched |
| `key` | [String](scalar#string) | preference type for which all preferences needs to be fetched |

**team** (`teamId`: [String](scalar#string)) : [TeamOutput](object#teamoutput)

Return team for given team Id

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `teamId` | [String](scalar#string) | Team Id |

**teams** (`employeeId`: [String!](scalar#string)) : [[TeamOutput]](object#teamoutput)

Returns list of all the teams for an employee

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String!](scalar#string) | Employee ID for which all teams needs to be fetched |

**allTeams**  : [[TeamOutput]](object#teamoutput)

Returns list of all the teams

**entitlements**  : [[String]](scalar#string)

Returns list of all groups of an employee

**topicCategories** (`topicId`: [String](scalar#string), `sortBy`: [String](scalar#string)) : [[Topic]](object#topic)

List of all topic role categories

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `topicId` | [String](scalar#string) | topic id |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by. |

**topicGroups** (`categoryId`: [String](scalar#string), `sortBy`: [String](scalar#string)) : [[RoleGroup]](object#rolegroup)

List all topic role groups

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `categoryId` | [String](scalar#string) | category id |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by. |

**PeopleAPIProfileQuery_Realtimecustomreport**  : [[String]](scalar#string)

<iframe src="https://www.site24x7.eu/public/dashboard/FBlvh5-GIjZQ09kmJ05p1Fwf7Ra0mG2BSCYyMVfmq2alBW5Tkx55s7bPHfqIzxvLEOtJnC8lr8dQtZG5e-rGOAuhQYjGHWTH4izoFkhk3JTrq3xlVKIiynzbPbiIhati" scrolling="yes" align="center" height="200" width="800" border="0" frameborder="0"></iframe>  <br />

**PeopleAPIResponseTime_Oneweektimelinedata**  : [[String]](scalar#string)

<iframe src="https://app.datadoghq.com/graph/embed?token=604d6baee98a8207f465840f9eeef3847bf06fa983bf64be7f6489793fbb61c5&height=200&width=400&legend=true" width="400" height="200" frameborder="0"></iframe> 

# PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.
<<<<<<< HEAD
**employees** (`ids`: [[String]](scalar#string), `dataSet`: [DataSet](dataset)) : [[Employee]](object#employee)
=======
**employees** (`ids`: [[String]](doc/scalar#string), `dataSet`: [DataSet](doc/enum#DataSet)) : [[Employee]](doc/object#employee)
>>>>>>> d66dea4f4d17c8be3955794f68f25e1e2b209759

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
<<<<<<< HEAD
| `ids` | [[String]](scalar#string) | Array of employee ids |
| `dataSet` | [DataSet](dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**employee** (`id`: [String](scalar#string), `field`: [String](scalar#string), `dataSet`: [DataSet](dataset)) : [Employee](object#employee)
=======
| `ids` | [[String]](doc/scalar#string) | Array of employee ids |
| `dataSet` | [DataSet](doc/enum#DataSet) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**employee** (`id`: [String](doc/scalar#string), `field`: [String](doc/scalar#string), `dataSet`: [DataSet](doc/enum#DataSet)) : [Employee](doc/object#employee)
>>>>>>> d66dea4f4d17c8be3955794f68f25e1e2b209759

Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
<<<<<<< HEAD
| `id` | [String](scalar#string) | Employee Id |
| `field` | [String](scalar#string) |  |
| `dataSet` | [DataSet](dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

`Deprecated`**search** (`find`: [String](scalar#string), `filter`: [String](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](dataset), `sortBy`: [String](scalar#string), `filters`: [[String]](scalar#string), `filterType`: [FilterType](filtertype)) : [[Employee]](object#employee)
=======
| `id` | [String](doc/scalar#string) | Employee Id |
| `field` | [String](doc/scalar#string) |  |
| `dataSet` | [DataSet](doc/enum#DataSet) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

`Deprecated`**search** (`find`: [String](doc/scalar#string), `filter`: [String](doc/scalar#string), `limit`: [Int](doc/scalar#int), `offset`: [Int](doc/scalar#int), `dataSet`: [DataSet](doc/enum#DataSet), `sortBy`: [String](doc/scalar#string), `filters`: [[String]](doc/scalar#string), `filterType`: [FilterType](doc/enum#FilterType)) : [[Employee]](doc/object#employee)
>>>>>>> d66dea4f4d17c8be3955794f68f25e1e2b209759
*Search has been deprecated, Use peopleSearch() instead*
DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
<<<<<<< HEAD
| `find` | [String](scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](filtertype) | Filter type OR/AND/NOT. Default is OR |

**peopleSearch** (`find`: [String](scalar#string), `filter`: [String](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](dataset), `sortBy`: [String](scalar#string), `filters`: [[String]](scalar#string), `filterType`: [FilterType](filtertype)) : [Employees](object#employees)
=======
| `find` | [String](doc/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](doc/scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](doc/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](doc/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](doc/enum#DataSet) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](doc/scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](doc/scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](doc/enum#FilterType) | Filter type OR/AND/NOT. Default is OR |

**peopleSearch** (`find`: [String](doc/scalar#string), `filter`: [String](doc/scalar#string), `limit`: [Int](doc/scalar#int), `offset`: [Int](doc/scalar#int), `dataSet`: [DataSet](dataset), `sortBy`: [String](doc/scalar#string), `filters`: [[String]](doc/scalar#string), `filterType`: [FilterType](doc/enum#FilterType)) : [Employees](doc/object#employees)
>>>>>>> d66dea4f4d17c8be3955794f68f25e1e2b209759

Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
<<<<<<< HEAD
| `find` | [String](scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](filtertype) | Filter type OR/AND/NOT. Default is OR |

**searchFilter** (`find`: [String](scalar#string), `filters`: [[search]](search), `resultFilters`: [[String]](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](dataset), `sortBy`: [String](scalar#string)) : [Employees](object#employees)
=======
| `find` | [String](doc/scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filter` | [String](doc/scalar#string) | Value of filter should be filter name followed by equalTo symbol(=) and then value eg : "hostOfficeCode=CHI" |
| `limit` | [Int](doc/scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](doc/scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](doc/enum#DataSet) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](doc/scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](doc/scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](doc/enum#FilterType) | Filter type OR/AND/NOT. Default is OR |

**searchFilter** (`find`: [String](doc/scalar#string), `filters`: [[search]](search), `resultFilters`: [[String]](doc/scalar#string), `limit`: [Int](doc/scalar#int), `offset`: [Int](doc/scalar#int), `dataSet`: [DataSet](doc/enum#DataSet), `sortBy`: [String](doc/scalar#string)) : [Employees](doc/object#employees)
>>>>>>> d66dea4f4d17c8be3955794f68f25e1e2b209759

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |
| `resultFilters` | [[String]](scalar#string) | Possible filters and available result counts |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |

**jobFunctions** (`dataSet`: [DataSet](dataset)) : [[JobFunction]](object#jobfunction)

Returns list of all distinct job functions

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](doc/enum#DataSet) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

**practiceAreas**  : [[PracticeArea]](object#practicearea)

Returns list of all practice area objects

<<<<<<< HEAD
**cohorts** (`dataSet`: [DataSet](dataset)) : [[String]](scalar#string)
=======
**cohorts** (`dataSet`: [DataSet](doc/enum#DataSet)) : [[String]](doc/scalar#string)
>>>>>>> d66dea4f4d17c8be3955794f68f25e1e2b209759

Returns list of all distinct cohorts

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `dataSet` | [DataSet](doc/enum#DataSet) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |

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
# PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.
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
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**searchFilter** (`find`: [String](scalar#string), `filters`: [[search]](search), `resultFilters`: [[String]](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](enum#dataset), `sortBy`: [String](scalar#string)) : [Employees](object#employees)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |
| `resultFilters` | [[String]](scalar#string) | Possible filters and available result counts |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |

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
# PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.
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
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |
| `filters` | [[String]](scalar#string) | Two or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**searchFilter** (`find`: [String](scalar#string), `filters`: [[search]](search), `resultFilters`: [[String]](scalar#string), `limit`: [Int](scalar#int), `offset`: [Int](scalar#int), `dataSet`: [DataSet](enum#dataset), `sortBy`: [String](scalar#string)) : [Employees](object#employees)

Lookup location by name, title or any other information you know. Returns the matching location objects as an array.

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `find` | [String](scalar#string) | Value of find should be an Employee name eg : "Lastname, Firstname" |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |
| `resultFilters` | [[String]](scalar#string) | Possible filters and available result counts |
| `limit` | [Int](scalar#int) | Size of the page. Default is 30. Works for both filter and find |
| `offset` | [Int](scalar#int) | Offset/start index of page. Default is 0. Works for both filter and find |
| `dataSet` | [DataSet](enum#dataset) | Data set type from which people data is to be accessed. Currently it is BCG_IT(only IT people) or BCG_ALL(BCG worldwide people) |
| `sortBy` | [String](scalar#string) | A field name by which the list is suppose to be ordered by |

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

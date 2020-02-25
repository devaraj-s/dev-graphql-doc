# Objects

## PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](locationapi/object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.  |
| `employee` | [Employee](locationapi/object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.  |
| `search` | [[Employee]](locationapi/object#employee) | DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees **Deprecated** |
| `peopleSearch` | [Employees](locationapi/object#employees) | Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.  |
| `searchFilter` | [Employees](locationapi/object#employees) | Lookup location by name, title or any other information you know. Returns the matching location objects as an array.  |
| `jobFunctions` | [[JobFunction]](locationapi/object#jobfunction) | Returns list of all distinct job functions  |
| `practiceAreas` | [[PracticeArea]](locationapi/object#practicearea) | Returns list of all practice area objects  |
| `cohorts` | [[String]](locationapi/scalar#string) | Returns list of all distinct cohorts  |
| `preferences` | [[OutputPreference]](locationapi/object#outputpreference) | Returns list of preferences  |
| `team` | [TeamOutput](locationapi/object#teamoutput) | Return team for given team Id  |
| `teams` | [[TeamOutput]](locationapi/object#teamoutput) | Returns list of all the teams for an employee  |
| `allTeams` | [[TeamOutput]](locationapi/object#teamoutput) | Returns list of all the teams  |
| `entitlements` | [[String]](locationapi/scalar#string) | Returns list of all groups of an employee  |

## Employee
Employee Type - the main data structure used by the People API graph. In a logical People graph, each node is an instance of this type.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](locationapi/scalar#string) | Employee's unique Id.  |
| `name` | [String](locationapi/scalar#string) | Full name of the Employee with 'Surname, Firstname' format.  |
| `displayName` | [String](locationapi/scalar#string) | Display name of the Employee with 'Surname Firstname' format.  |
| `firstName` | [String](locationapi/scalar#string) | Employee's first name.  |
| `lastName` | [String](locationapi/scalar#string) | Employee's last name.  |
| `slackId` | [String](locationapi/scalar#string) | Employee's Slack alias  |
| `title` | [String](locationapi/scalar#string) | Employee's Business title.  |
| `cohort` | [String](locationapi/scalar#string) | Employee's cohort  |
| `status` | [String](locationapi/scalar#string) | Employee's status Active/Inactive/LOA  |
| `jobFunction` | [String](locationapi/scalar#string) | Employee's job function  |
| `globalTitle` | [String](locationapi/scalar#string) | Employee's global title  |
| `email` | [String](locationapi/scalar#string) | Employee's official email.  |
| `phone` | [String](locationapi/scalar#string) | Employee's official phone.  |
| `mobile` | [String](locationapi/scalar#string) | Employee's official mobile phone.  |
| `nationality` | [String](locationapi/scalar#string) | Employee's nationality  |
| `hireDate` | [String](locationapi/scalar#string) | Employee's hiring date (timestamp)  |
| `hostOfficeId` | [String](locationapi/scalar#string) | Employee's host office code, where the employee is currently based  |
| `hostOfficeRegion` | [String](locationapi/scalar#string) | Host office region  |
| `homeOfficeId` | [String](locationapi/scalar#string) | Employee's home office code  |
| `homeOfficeRegion` | [String](locationapi/scalar#string) | Employee's home office region  |
| `location` | [String](locationapi/scalar#string) | DEPRECATED - location has been deprecated. Use hostLocation { officeCode } or hostOfficeCode instead , Employee's host office location code, where the employee is currently based  |
| `hostOfficeLocation` | [Location](locationapi/object#location) | Employee's host office location object, where the employee is currently based.  |
| `homeOfficeLocation` | [Location](locationapi/object#location) | Employee's home office location object, where the employee is from.  |
| `picture` | [String](locationapi/scalar#string) | Employee's profile pic in jpeg format.  |
| `profilePicture` | [String](locationapi/scalar#string) | Employee's profile pic in jpeg format.  |
| `lineManagerId` | [String](locationapi/scalar#string) | Line Manager's Id.  |
| `lineManager` | [Employee](locationapi/object#employee) | Line Manager, returned as an Employee object.  |
| `reportingLine` | [[Employee]](locationapi/object#employee) | Reporting line of the employee. Returned as an array of Employee objects.  |
| `lastUpdated` | [String](locationapi/scalar#string) | Timestamp when people api updated itself with the snowflake  |
| `preferences` | [[OutputPreference]](locationapi/object#outputpreference) | Preferences of employee  |
| `practiceArea` | [String](locationapi/scalar#string) | Practice area the employee belongs to  |
| `practiceAreas` | [[PracticeAreaInfo]](locationapi/object#practiceareainfo) | Practice areas details of an employee  |
| `responsibilityCenterId` | [String](locationapi/scalar#string) | Employee's responsibility center Id  |
| `responsibilityCenterName` | [String](locationapi/scalar#string) | Employee's responsibility center name  |
| `responsibilityPercentage` | [String](locationapi/scalar#string) | Employee's responsibility percentage  |
| `responsibilityGroupName` | [String](locationapi/scalar#string) | Employee's responsibility group name  |

## Location
Location Type - object for the office location

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](locationapi/scalar#string) | Unique office code  |
| `name` | [String](locationapi/scalar#string) | Office name  |
| `regionId` | [String](locationapi/scalar#string) | Unique region id of the office  |
| `street` | [String](locationapi/scalar#string) | Street where office is located  |
| `street2` | [String](locationapi/scalar#string) | Street where office is located  |
| `street3` | [String](locationapi/scalar#string) | Street where office is located  |
| `city` | [String](locationapi/scalar#string) | City of office  |
| `state` | [String](locationapi/scalar#string) | State of Office  |
| `zipCode` | [String](locationapi/scalar#string) | Zip-code of office  |
| `country` | [String](locationapi/scalar#string) | Country of office  |
| `countryCode` | [String](locationapi/scalar#string) | Country code of office  |
| `geoLocation` | [GeoLocation](locationapi/object#geolocation) | Geolocation has latitude and longitude  |
| `phone` | [String](locationapi/scalar#string) | Phone number of office  |
| `imageUrl` | [String](locationapi/scalar#string) | Link to an office image  |
| `contentLinks` | [[ContentType]](locationapi/object#contenttype) | Contents inside the office location  |
| `timezone` | [String](locationapi/scalar#string) | Time zone of the location  |
| `weather` | [Weather](locationapi/object#weather) | current weather for the location  |

## GeoLocation
GeoLocation Type - object for latitude and longitude

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `lat` | [String](locationapi/scalar#string) | Latitude of a geo location  |
| `lon` | [String](locationapi/scalar#string) | Longitude of a geo location  |

## ContentType
Object representation for the ContentLink

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](locationapi/scalar#string) | Name of the content  |
| `link` | [String](locationapi/scalar#string) | Link to the content  |
| `image` | [String](locationapi/scalar#string) | Icon name for the content  |

## Weather
Weather Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `icon` | [String](locationapi/scalar#string) | Weather icon to be used  |
| `description` | [String](locationapi/scalar#string) | Weather description of the description  |
| `temperature` | [[WeatherUnit]](locationapi/object#weatherunit) | Temperature in both celcius and farenheit  |

## WeatherUnit
Weather Unit Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `type` | [String](locationapi/scalar#string) | Unit Type- Celcius or Farenheit  |
| `value` | [Float](locationapi/scalar#float) | Current temperature  |

## OutputPreference
Output preference object

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String](locationapi/scalar#string) | Employee Id  |
| `key` | [String](locationapi/scalar#string) | Preferences name  |
| `values` | [[ValueType]](locationapi/object#valuetype) | Preferences values  |

## ValueType
Preference representation

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](locationapi/scalar#string) | Preferred employee id  |
| `type` | [String](locationapi/scalar#string) | Preference type. Default is string  |
| `timestamp` | [String](locationapi/scalar#string) | Epoch Timestamp number  |

## PracticeAreaInfo
Practice Area Details

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `Level` | [String](locationapi/scalar#string) | Level of expertise  |
| `Topic` | [String](locationapi/scalar#string) | Topic of the practice area  |
| `Type` | [String](locationapi/scalar#string) | Practice area type  |

## Employees
List of employees for search result with total number of employees actually exists for seach query provided

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](locationapi/object#employee) | List of employee objects  |
| `totalCount` | [Int](locationapi/scalar#int) | The total number of matching employees for the search query exists in data base, regardless of limit provided  |
| `searchFilters` | [[SearchResultFilterType]](locationapi/object#searchresultfiltertype) |   |

## SearchResultFilterType
SearchResultFilter 

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `field` | [String](locationapi/scalar#string) | FIlter Field Value  |
| `filters` | [[ResultFilterType]](locationapi/object#resultfiltertype) |    |

## ResultFilterType
ResultFilterType 

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `key` | [String](locationapi/scalar#string) | FIlter Field Value  |
| `doc_count` | [String](locationapi/scalar#string) | Longitude of a geo location  |

## JobFunction
Object representation for a Job Function

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](locationapi/scalar#string) | Name of the Job Function  |

## PracticeArea
Object representation for the Practice Area

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](locationapi/scalar#string) | Name of the practice area  |
| `category` | [String](locationapi/scalar#string) | Category of pracitce area  |
| `topics` | [[PracticeAreaTopic]](locationapi/object#practiceareatopic) | Topics inside practice area  |
| `imageUrl` | [String](locationapi/scalar#string) | URL of the practice area image  |
| `homeUrl` | [String](locationapi/scalar#string) | Home Url in practice are  |
| `contentLinks` | [[ContentType]](locationapi/object#contenttype) | Contents inside the practice area  |

## PracticeAreaTopic
Object representation for the Practice Area Topic

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](locationapi/scalar#string) | Name of the topic  |

## TeamOutput
Team data

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](locationapi/scalar#string) | Team Id  |
| `name` | [String](locationapi/scalar#string) | Team name  |
| `summary` | [String](locationapi/scalar#string) | Team information summary  |
| `slackURL` | [String](locationapi/scalar#string) | Team slack URL  |
| `egnyteURL` | [String](locationapi/scalar#string) | Team egnyte URL  |
| `image` | [String](locationapi/scalar#string) | Image for the team  |
| `imageName` | [String](locationapi/scalar#string) | Image for the team  |
| `employeeIds` | [[String]](locationapi/scalar#string) | Employee Ids of team members  |
| `contentLinks` | [[ContentType]](locationapi/object#contenttype) | Contents links for team  |

## PreferncesAPIMutation
Graph based mutation to store an employee's preferences and create teams

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `preference` | [OutputPreference](locationapi/object#outputpreference) | Add user preferences  |
| `team` | [TeamOutput](locationapi/object#teamoutput) | Create Team  |
| `deleteTeam` | [TeamOutput](locationapi/object#teamoutput) | Delete Team  |
| `updateTeam` | [TeamOutput](locationapi/object#teamoutput) | Update Team  |

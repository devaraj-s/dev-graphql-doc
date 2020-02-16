# Objects

## PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](doc/object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.  |
| `employee` | [Employee](doc/object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.  |
| `search` | [[Employee]](doc/object#employee) | DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees **Deprecated** |
| `peopleSearch` | [Employees](doc/object#employees) | Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.  |
| `searchFilter` | [Employees](doc/object#employees) | Lookup location by name, title or any other information you know. Returns the matching location objects as an array.  |
| `jobFunctions` | [[JobFunction]](doc/object#jobfunction) | Returns list of all distinct job functions  |
| `practiceAreas` | [[PracticeArea]](doc/object#practicearea) | Returns list of all practice area objects  |
| `cohorts` | [[String]](doc/scalar#string) | Returns list of all distinct cohorts  |
| `preferences` | [[OutputPreference]](doc/object#outputpreference) | Returns list of preferences  |
| `team` | [TeamOutput](doc/object#teamoutput) | Return team for given team Id  |
| `teams` | [[TeamOutput]](doc/object#teamoutput) | Returns list of all the teams for an employee  |
| `allTeams` | [[TeamOutput]](doc/object#teamoutput) | Returns list of all the teams  |
| `entitlements` | [[String]](doc/scalar#string) | Returns list of all groups of an employee  |

## Employee
Employee Type - the main data structure used by the People API graph. In a logical People graph, each node is an instance of this type.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](doc/scalar#string) | Employee's unique Id.  |
| `name` | [String](doc/scalar#string) | Full name of the Employee with 'Surname, Firstname' format.  |
| `displayName` | [String](doc/scalar#string) | Display name of the Employee with 'Surname Firstname' format.  |
| `firstName` | [String](doc/scalar#string) | Employee's first name.  |
| `lastName` | [String](doc/scalar#string) | Employee's last name.  |
| `slackId` | [String](doc/scalar#string) | Employee's Slack alias  |
| `title` | [String](doc/scalar#string) | Employee's Business title.  |
| `cohort` | [String](doc/scalar#string) | Employee's cohort  |
| `status` | [String](doc/scalar#string) | Employee's status Active/Inactive/LOA  |
| `jobFunction` | [String](doc/scalar#string) | Employee's job function  |
| `globalTitle` | [String](doc/scalar#string) | Employee's global title  |
| `email` | [String](doc/scalar#string) | Employee's official email.  |
| `phone` | [String](doc/scalar#string) | Employee's official phone.  |
| `mobile` | [String](doc/scalar#string) | Employee's official mobile phone.  |
| `nationality` | [String](doc/scalar#string) | Employee's nationality  |
| `hireDate` | [String](doc/scalar#string) | Employee's hiring date (timestamp)  |
| `hostOfficeId` | [String](doc/scalar#string) | Employee's host office code, where the employee is currently based  |
| `hostOfficeRegion` | [String](doc/scalar#string) | Host office region  |
| `homeOfficeId` | [String](doc/scalar#string) | Employee's home office code  |
| `homeOfficeRegion` | [String](doc/scalar#string) | Employee's home office region  |
| `location` | [String](doc/scalar#string) | DEPRECATED - location has been deprecated. Use hostLocation { officeCode } or hostOfficeCode instead , Employee's host office location code, where the employee is currently based  |
| `hostOfficeLocation` | [Location](doc/object#location) | Employee's host office location object, where the employee is currently based.  |
| `homeOfficeLocation` | [Location](doc/object#location) | Employee's home office location object, where the employee is from.  |
| `picture` | [String](doc/scalar#string) | Employee's profile pic in jpeg format.  |
| `profilePicture` | [String](doc/scalar#string) | Employee's profile pic in jpeg format.  |
| `lineManagerId` | [String](doc/scalar#string) | Line Manager's Id.  |
| `lineManager` | [Employee](doc/object#employee) | Line Manager, returned as an Employee object.  |
| `reportingLine` | [[Employee]](doc/object#employee) | Reporting line of the employee. Returned as an array of Employee objects.  |
| `lastUpdated` | [String](doc/scalar#string) | Timestamp when people api updated itself with the snowflake  |
| `preferences` | [[OutputPreference]](doc/object#outputpreference) | Preferences of employee  |
| `practiceArea` | [String](doc/scalar#string) | Practice area the employee belongs to  |
| `practiceAreas` | [[PracticeAreaInfo]](doc/object#practiceareainfo) | Practice areas details of an employee  |
| `responsibilityCenterId` | [String](doc/scalar#string) | Employee's responsibility center Id  |
| `responsibilityCenterName` | [String](doc/scalar#string) | Employee's responsibility center name  |
| `responsibilityPercentage` | [String](doc/scalar#string) | Employee's responsibility percentage  |
| `responsibilityGroupName` | [String](doc/scalar#string) | Employee's responsibility group name  |

## Location
Location Type - object for the office location

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](doc/scalar#string) | Unique office code  |
| `name` | [String](doc/scalar#string) | Office name  |
| `regionId` | [String](doc/scalar#string) | Unique region id of the office  |
| `street` | [String](doc/scalar#string) | Street where office is located  |
| `street2` | [String](doc/scalar#string) | Street where office is located  |
| `street3` | [String](doc/scalar#string) | Street where office is located  |
| `city` | [String](doc/scalar#string) | City of office  |
| `state` | [String](doc/scalar#string) | State of Office  |
| `zipCode` | [String](doc/scalar#string) | Zip-code of office  |
| `country` | [String](doc/scalar#string) | Country of office  |
| `countryCode` | [String](doc/scalar#string) | Country code of office  |
| `geoLocation` | [GeoLocation](doc/object#geolocation) | Geolocation has latitude and longitude  |
| `phone` | [String](doc/scalar#string) | Phone number of office  |
| `imageUrl` | [String](doc/scalar#string) | Link to an office image  |
| `contentLinks` | [[ContentType]](doc/object#contenttype) | Contents inside the office location  |
| `timezone` | [String](doc/scalar#string) | Time zone of the location  |
| `weather` | [Weather](doc/object#weather) | current weather for the location  |

## GeoLocation
GeoLocation Type - object for latitude and longitude

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `lat` | [String](doc/scalar#string) | Latitude of a geo location  |
| `lon` | [String](doc/scalar#string) | Longitude of a geo location  |

## ContentType
Object representation for the ContentLink

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](doc/scalar#string) | Name of the content  |
| `link` | [String](doc/scalar#string) | Link to the content  |
| `image` | [String](doc/scalar#string) | Icon name for the content  |

## Weather
Weather Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `icon` | [String](doc/scalar#string) | Weather icon to be used  |
| `description` | [String](doc/scalar#string) | Weather description of the description  |
| `temperature` | [[WeatherUnit]](doc/object#weatherunit) | Temperature in both celcius and farenheit  |

## WeatherUnit
Weather Unit Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `type` | [String](doc/scalar#string) | Unit Type- Celcius or Farenheit  |
| `value` | [Float](doc/scalar#float) | Current temperature  |

## OutputPreference
Output preference object

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String](doc/scalar#string) | Employee Id  |
| `key` | [String](doc/scalar#string) | Preferences name  |
| `values` | [[ValueType]](doc/object#valuetype) | Preferences values  |

## ValueType
Preference representation

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](doc/scalar#string) | Preferred employee id  |
| `type` | [String](doc/scalar#string) | Preference type. Default is string  |
| `timestamp` | [String](doc/scalar#string) | Epoch Timestamp number  |

## PracticeAreaInfo
Practice Area Details

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `Level` | [String](doc/scalar#string) | Level of expertise  |
| `Topic` | [String](doc/scalar#string) | Topic of the practice area  |
| `Type` | [String](doc/scalar#string) | Practice area type  |

## Employees
List of employees for search result with total number of employees actually exists for seach query provided

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](doc/object#employee) | List of employee objects  |
| `totalCount` | [Int](doc/scalar#int) | The total number of matching employees for the search query exists in data base, regardless of limit provided  |
| `searchFilters` | [[SearchResultFilterType]](doc/object#searchresultfiltertype) |   |

## SearchResultFilterType
SearchResultFilter 

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `field` | [String](doc/scalar#string) | FIlter Field Value  |
| `filters` | [[ResultFilterType]](doc/object#resultfiltertype) |    |

## ResultFilterType
ResultFilterType 

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `key` | [String](doc/scalar#string) | FIlter Field Value  |
| `count` | [String](doc/scalar#string) | Longitude of a geo location  |

## JobFunction
Object representation for a Job Function

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](doc/scalar#string) | Name of the Job Function  |

## PracticeArea
Object representation for the Practice Area

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](doc/scalar#string) | Name of the practice area  |
| `category` | [String](doc/scalar#string) | Category of pracitce area  |
| `topics` | [[PracticeAreaTopic]](doc/object#practiceareatopic) | Topics inside practice area  |
| `imageUrl` | [String](doc/scalar#string) | URL of the practice area image  |
| `homeUrl` | [String](doc/scalar#string) | Home Url in practice are  |
| `contentLinks` | [[ContentType]](doc/object#contenttype) | Contents inside the practice area  |

## PracticeAreaTopic
Object representation for the Practice Area Topic

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](doc/scalar#string) | Name of the topic  |

## TeamOutput
Team data

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](doc/scalar#string) | Team Id  |
| `name` | [String](doc/scalar#string) | Team name  |
| `summary` | [String](doc/scalar#string) | Team information summary  |
| `slackURL` | [String](doc/scalar#string) | Team slack URL  |
| `egnyteURL` | [String](doc/scalar#string) | Team egnyte URL  |
| `image` | [String](doc/scalar#string) | Image for the team  |
| `imageName` | [String](doc/scalar#string) | Image for the team  |
| `employeeIds` | [[String]](doc/scalar#string) | Employee Ids of team members  |
| `contentLinks` | [[ContentType]](doc/object#contenttype) | Contents links for team  |

## PreferncesAPIMutation
Graph based mutation to store an employee's preferences and create teams

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `preference` | [OutputPreference](doc/object#outputpreference) | Add user preferences  |
| `team` | [TeamOutput](doc/object#teamoutput) | Create Team  |
| `deleteTeam` | [TeamOutput](doc/object#teamoutput) | Delete Team  |
| `updateTeam` | [TeamOutput](doc/object#teamoutput) | Update Team  |

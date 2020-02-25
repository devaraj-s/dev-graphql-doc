# Objects

## PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](eventsapi/object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.  |
| `employee` | [Employee](eventsapi/object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.  |
| `search` | [[Employee]](eventsapi/object#employee) | DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees **Deprecated** |
| `peopleSearch` | [Employees](eventsapi/object#employees) | Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.  |
| `searchFilter` | [Employees](eventsapi/object#employees) | Lookup location by name, title or any other information you know. Returns the matching location objects as an array.  |
| `jobFunctions` | [[JobFunction]](eventsapi/object#jobfunction) | Returns list of all distinct job functions  |
| `practiceAreas` | [[PracticeArea]](eventsapi/object#practicearea) | Returns list of all practice area objects  |
| `cohorts` | [[String]](eventsapi/scalar#string) | Returns list of all distinct cohorts  |
| `preferences` | [[OutputPreference]](eventsapi/object#outputpreference) | Returns list of preferences  |
| `team` | [TeamOutput](eventsapi/object#teamoutput) | Return team for given team Id  |
| `teams` | [[TeamOutput]](eventsapi/object#teamoutput) | Returns list of all the teams for an employee  |
| `allTeams` | [[TeamOutput]](eventsapi/object#teamoutput) | Returns list of all the teams  |
| `entitlements` | [[String]](eventsapi/scalar#string) | Returns list of all groups of an employee  |

## Employee
Employee Type - the main data structure used by the People API graph. In a logical People graph, each node is an instance of this type.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](eventsapi/scalar#string) | Employee's unique Id.  |
| `name` | [String](eventsapi/scalar#string) | Full name of the Employee with 'Surname, Firstname' format.  |
| `displayName` | [String](eventsapi/scalar#string) | Display name of the Employee with 'Surname Firstname' format.  |
| `firstName` | [String](eventsapi/scalar#string) | Employee's first name.  |
| `lastName` | [String](eventsapi/scalar#string) | Employee's last name.  |
| `slackId` | [String](eventsapi/scalar#string) | Employee's Slack alias  |
| `title` | [String](eventsapi/scalar#string) | Employee's Business title.  |
| `cohort` | [String](eventsapi/scalar#string) | Employee's cohort  |
| `status` | [String](eventsapi/scalar#string) | Employee's status Active/Inactive/LOA  |
| `jobFunction` | [String](eventsapi/scalar#string) | Employee's job function  |
| `globalTitle` | [String](eventsapi/scalar#string) | Employee's global title  |
| `email` | [String](eventsapi/scalar#string) | Employee's official email.  |
| `phone` | [String](eventsapi/scalar#string) | Employee's official phone.  |
| `mobile` | [String](eventsapi/scalar#string) | Employee's official mobile phone.  |
| `nationality` | [String](eventsapi/scalar#string) | Employee's nationality  |
| `hireDate` | [String](eventsapi/scalar#string) | Employee's hiring date (timestamp)  |
| `hostOfficeId` | [String](eventsapi/scalar#string) | Employee's host office code, where the employee is currently based  |
| `hostOfficeRegion` | [String](eventsapi/scalar#string) | Host office region  |
| `homeOfficeId` | [String](eventsapi/scalar#string) | Employee's home office code  |
| `homeOfficeRegion` | [String](eventsapi/scalar#string) | Employee's home office region  |
| `location` | [String](eventsapi/scalar#string) | DEPRECATED - location has been deprecated. Use hostLocation { officeCode } or hostOfficeCode instead , Employee's host office location code, where the employee is currently based  |
| `hostOfficeLocation` | [Location](eventsapi/object#location) | Employee's host office location object, where the employee is currently based.  |
| `homeOfficeLocation` | [Location](eventsapi/object#location) | Employee's home office location object, where the employee is from.  |
| `picture` | [String](eventsapi/scalar#string) | Employee's profile pic in jpeg format.  |
| `profilePicture` | [String](eventsapi/scalar#string) | Employee's profile pic in jpeg format.  |
| `lineManagerId` | [String](eventsapi/scalar#string) | Line Manager's Id.  |
| `lineManager` | [Employee](eventsapi/object#employee) | Line Manager, returned as an Employee object.  |
| `reportingLine` | [[Employee]](eventsapi/object#employee) | Reporting line of the employee. Returned as an array of Employee objects.  |
| `lastUpdated` | [String](eventsapi/scalar#string) | Timestamp when people api updated itself with the snowflake  |
| `preferences` | [[OutputPreference]](eventsapi/object#outputpreference) | Preferences of employee  |
| `practiceArea` | [String](eventsapi/scalar#string) | Practice area the employee belongs to  |
| `practiceAreas` | [[PracticeAreaInfo]](eventsapi/object#practiceareainfo) | Practice areas details of an employee  |
| `responsibilityCenterId` | [String](eventsapi/scalar#string) | Employee's responsibility center Id  |
| `responsibilityCenterName` | [String](eventsapi/scalar#string) | Employee's responsibility center name  |
| `responsibilityPercentage` | [String](eventsapi/scalar#string) | Employee's responsibility percentage  |
| `responsibilityGroupName` | [String](eventsapi/scalar#string) | Employee's responsibility group name  |

## Location
Location Type - object for the office location

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](eventsapi/scalar#string) | Unique office code  |
| `name` | [String](eventsapi/scalar#string) | Office name  |
| `regionId` | [String](eventsapi/scalar#string) | Unique region id of the office  |
| `street` | [String](eventsapi/scalar#string) | Street where office is located  |
| `street2` | [String](eventsapi/scalar#string) | Street where office is located  |
| `street3` | [String](eventsapi/scalar#string) | Street where office is located  |
| `city` | [String](eventsapi/scalar#string) | City of office  |
| `state` | [String](eventsapi/scalar#string) | State of Office  |
| `zipCode` | [String](eventsapi/scalar#string) | Zip-code of office  |
| `country` | [String](eventsapi/scalar#string) | Country of office  |
| `countryCode` | [String](eventsapi/scalar#string) | Country code of office  |
| `geoLocation` | [GeoLocation](eventsapi/object#geolocation) | Geolocation has latitude and longitude  |
| `phone` | [String](eventsapi/scalar#string) | Phone number of office  |
| `imageUrl` | [String](eventsapi/scalar#string) | Link to an office image  |
| `contentLinks` | [[ContentType]](eventsapi/object#contenttype) | Contents inside the office location  |
| `timezone` | [String](eventsapi/scalar#string) | Time zone of the location  |
| `weather` | [Weather](eventsapi/object#weather) | current weather for the location  |

## GeoLocation
GeoLocation Type - object for latitude and longitude

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `lat` | [String](eventsapi/scalar#string) | Latitude of a geo location  |
| `lon` | [String](eventsapi/scalar#string) | Longitude of a geo location  |

## ContentType
Object representation for the ContentLink

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](eventsapi/scalar#string) | Name of the content  |
| `link` | [String](eventsapi/scalar#string) | Link to the content  |
| `image` | [String](eventsapi/scalar#string) | Icon name for the content  |

## Weather
Weather Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `icon` | [String](eventsapi/scalar#string) | Weather icon to be used  |
| `description` | [String](eventsapi/scalar#string) | Weather description of the description  |
| `temperature` | [[WeatherUnit]](eventsapi/object#weatherunit) | Temperature in both celcius and farenheit  |

## WeatherUnit
Weather Unit Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `type` | [String](eventsapi/scalar#string) | Unit Type- Celcius or Farenheit  |
| `value` | [Float](eventsapi/scalar#float) | Current temperature  |

## OutputPreference
Output preference object

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String](eventsapi/scalar#string) | Employee Id  |
| `key` | [String](eventsapi/scalar#string) | Preferences name  |
| `values` | [[ValueType]](eventsapi/object#valuetype) | Preferences values  |

## ValueType
Preference representation

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](eventsapi/scalar#string) | Preferred employee id  |
| `type` | [String](eventsapi/scalar#string) | Preference type. Default is string  |
| `timestamp` | [String](eventsapi/scalar#string) | Epoch Timestamp number  |

## PracticeAreaInfo
Practice Area Details

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `Level` | [String](eventsapi/scalar#string) | Level of expertise  |
| `Topic` | [String](eventsapi/scalar#string) | Topic of the practice area  |
| `Type` | [String](eventsapi/scalar#string) | Practice area type  |

## Employees
List of employees for search result with total number of employees actually exists for seach query provided

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](eventsapi/object#employee) | List of employee objects  |
| `totalCount` | [Int](eventsapi/scalar#int) | The total number of matching employees for the search query exists in data base, regardless of limit provided  |
| `searchFilters` | [[SearchResultFilterType]](eventsapi/object#searchresultfiltertype) |   |

## SearchResultFilterType
SearchResultFilter 

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `field` | [String](eventsapi/scalar#string) | FIlter Field Value  |
| `filters` | [[ResultFilterType]](eventsapi/object#resultfiltertype) |    |

## ResultFilterType
ResultFilterType 

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `key` | [String](eventsapi/scalar#string) | FIlter Field Value  |
| `doc_count` | [String](eventsapi/scalar#string) | Longitude of a geo location  |

## JobFunction
Object representation for a Job Function

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](eventsapi/scalar#string) | Name of the Job Function  |

## PracticeArea
Object representation for the Practice Area

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](eventsapi/scalar#string) | Name of the practice area  |
| `category` | [String](eventsapi/scalar#string) | Category of pracitce area  |
| `topics` | [[PracticeAreaTopic]](eventsapi/object#practiceareatopic) | Topics inside practice area  |
| `imageUrl` | [String](eventsapi/scalar#string) | URL of the practice area image  |
| `homeUrl` | [String](eventsapi/scalar#string) | Home Url in practice are  |
| `contentLinks` | [[ContentType]](eventsapi/object#contenttype) | Contents inside the practice area  |

## PracticeAreaTopic
Object representation for the Practice Area Topic

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](eventsapi/scalar#string) | Name of the topic  |

## TeamOutput
Team data

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](eventsapi/scalar#string) | Team Id  |
| `name` | [String](eventsapi/scalar#string) | Team name  |
| `summary` | [String](eventsapi/scalar#string) | Team information summary  |
| `slackURL` | [String](eventsapi/scalar#string) | Team slack URL  |
| `egnyteURL` | [String](eventsapi/scalar#string) | Team egnyte URL  |
| `image` | [String](eventsapi/scalar#string) | Image for the team  |
| `imageName` | [String](eventsapi/scalar#string) | Image for the team  |
| `employeeIds` | [[String]](eventsapi/scalar#string) | Employee Ids of team members  |
| `contentLinks` | [[ContentType]](eventsapi/object#contenttype) | Contents links for team  |

## PreferncesAPIMutation
Graph based mutation to store an employee's preferences and create teams

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `preference` | [OutputPreference](eventsapi/object#outputpreference) | Add user preferences  |
| `team` | [TeamOutput](eventsapi/object#teamoutput) | Create Team  |
| `deleteTeam` | [TeamOutput](eventsapi/object#teamoutput) | Delete Team  |
| `updateTeam` | [TeamOutput](eventsapi/object#teamoutput) | Update Team  |

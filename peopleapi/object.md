# Objects

## PeopleAPI
Graph based API to get People or Employee information, including their relationships like line managers, reporting line and office location. You can use an Employee query if employee id is known or use a Search query to look up an Employee.<br /><br />**CodeSamples:** [[Code]](peopleapi_code#Code) <br /><br />

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.  |
| `employee` | [Employee](object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.  |
| `search` | [[Employee]](object#employee) | DEPRECATED -  Search has been deprecated, Use peopleSearch() instead, Lookup employee by name, title or any other information you know. Returns a list of employees **Deprecated** |
| `peopleSearch` | [Employees](object#employees) | Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.  |
| `searchFilter` | [Employees](object#employees) | Lookup location by name, title or any other information you know. Returns the matching location objects as an array.  |
| `jobFunctions` | [[JobFunction]](object#jobfunction) | Returns list of all distinct job functions  |
| `practiceAreas` | [[PracticeArea]](object#practicearea) | Returns list of all practice area objects  |
| `cohorts` | [[String]](scalar#string) | Returns list of all distinct cohorts  |
| `preferences` | [[OutputPreference]](object#outputpreference) | Returns list of preferences  |
| `team` | [TeamOutput](object#teamoutput) | Return team for given team Id  |
| `teams` | [[TeamOutput]](object#teamoutput) | Returns list of all the teams for an employee  |
| `allTeams` | [[TeamOutput]](object#teamoutput) | Returns list of all the teams  |
| `entitlements` | [[String]](scalar#string) | Returns list of all groups of an employee  |
| `topicCategories` | [[Topic]](object#topic) | List of all topic role categories  |
| `topicGroups` | [[RoleGroup]](object#rolegroup) | List all topic role groups  |
| `PeopleAPIProfileQuery_Realtimecustomreport` | [[String]](scalar#string) | <iframe src="https://www.site24x7.eu/public/dashboard/FBlvh5-GIjZQ09kmJ05p1Fwf7Ra0mG2BSCYyMVfmq2alBW5Tkx55s7bPHfqIzxvLEOtJnC8lr8dQtZG5e-rGOAuhQYjGHWTH4izoFkhk3JTrq3xlVKIiynzbPbiIhati" scrolling="yes" align="center" height="200" width="800" border="0" frameborder="0"></iframe>  <br />  |
| `PeopleAPIResponseTime_Oneweektimelinedata` | [[String]](scalar#string) | <iframe src="https://app.datadoghq.com/graph/embed?token=604d6baee98a8207f465840f9eeef3847bf06fa983bf64be7f6489793fbb61c5&height=200&width=400&legend=true" width="400" height="200" frameborder="0"></iframe>   |

## Employee
Employee Type - the main data structure used by the People API graph. In a logical People graph, each node is an instance of this type.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Employee's unique Id.  |
| `name` | [String](scalar#string) | Full name of the Employee with 'Surname, Firstname' format.  |
| `displayName` | [String](scalar#string) | Display name of the Employee with 'Surname Firstname' format.  |
| `firstName` | [String](scalar#string) | Employee's first name.  |
| `lastName` | [String](scalar#string) | Employee's last name.  |
| `slackId` | [String](scalar#string) | Employee's Slack alias  |
| `title` | [String](scalar#string) | Employee's Business title.  |
| `cohort` | [String](scalar#string) | Employee's cohort  |
| `status` | [String](scalar#string) | Employee's status Active/Inactive/LOA  |
| `jobFunction` | [String](scalar#string) | Employee's job function  |
| `globalTitle` | [String](scalar#string) | Employee's global title  |
| `email` | [String](scalar#string) | Employee's official email.  |
| `phone` | [String](scalar#string) | Employee's official phone.  |
| `mobile` | [String](scalar#string) | Employee's official mobile phone.  |
| `nationality` | [String](scalar#string) | Employee's nationality  |
| `hireDate` | [String](scalar#string) | Employee's hiring date (timestamp)  |
| `hostOfficeId` | [String](scalar#string) | Employee's host office code, where the employee is currently based  |
| `hostOfficeRegion` | [String](scalar#string) | Host office region  |
| `homeOfficeId` | [String](scalar#string) | Employee's home office code  |
| `homeOfficeRegion` | [String](scalar#string) | Employee's home office region  |
| `location` | [String](scalar#string) | DEPRECATED - location has been deprecated. Use hostLocation { officeCode } or hostOfficeCode instead , Employee's host office location code, where the employee is currently based  |
| `hostOfficeLocation` | [Location](object#location) | Employee's host office location object, where the employee is currently based.  |
| `homeOfficeLocation` | [Location](object#location) | Employee's home office location object, where the employee is from.  |
| `picture` | [String](scalar#string) | Employee's profile pic in jpeg format.  |
| `profilePicture` | [String](scalar#string) | Employee's profile pic in jpeg format.  |
| `lineManagerId` | [String](scalar#string) | Line Manager's Id.  |
| `lineManager` | [Employee](object#employee) | Line Manager, returned as an Employee object.  |
| `reportingLine` | [[Employee]](object#employee) | Reporting line of the employee. Returned as an array of Employee objects.  |
| `lastUpdated` | [String](scalar#string) | Timestamp when people api updated itself with the snowflake  |
| `preferences` | [[OutputPreference]](object#outputpreference) | Preferences of employee  |
| `practiceArea` | [String](scalar#string) | Practice area the employee belongs to  |
| `practiceAreas` | [[PracticeAreaInfo]](object#practiceareainfo) | Practice areas details of an employee  |
| `responsibilityCenterId` | [String](scalar#string) | Employee's responsibility center Id  |
| `responsibilityCenterName` | [String](scalar#string) | Employee's responsibility center name  |
| `responsibilityPercentage` | [String](scalar#string) | Employee's responsibility percentage  |
| `responsibilityGroupName` | [String](scalar#string) | Employee's responsibility group name  |

## Location
Location Type - object for the office location

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Unique office code  |
| `name` | [String](scalar#string) | Office name  |
| `regionId` | [String](scalar#string) | Unique region id of the office  |
| `street` | [String](scalar#string) | Street where office is located  |
| `street2` | [String](scalar#string) | Street where office is located  |
| `street3` | [String](scalar#string) | Street where office is located  |
| `city` | [String](scalar#string) | City of office  |
| `state` | [String](scalar#string) | State of Office  |
| `zipCode` | [String](scalar#string) | Zip-code of office  |
| `country` | [String](scalar#string) | Country of office  |
| `countryCode` | [String](scalar#string) | Country code of office  |
| `geoLocation` | [GeoLocation](object#geolocation) | Geolocation has latitude and longitude  |
| `phone` | [String](scalar#string) | Phone number of office  |
| `imageUrl` | [String](scalar#string) | Link to an office image  |
| `contentLinks` | [[ContentType]](object#contenttype) | Contents inside the office location  |
| `timezone` | [String](scalar#string) | Time zone of the location  |
| `weather` | [Weather](object#weather) | current weather for the location  |

## GeoLocation
GeoLocation Type - object for latitude and longitude

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `lat` | [String](scalar#string) | Latitude of a geo location  |
| `lon` | [String](scalar#string) | Longitude of a geo location  |

## ContentType
Object representation for the ContentLink

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](scalar#string) | Name of the content  |
| `link` | [String](scalar#string) | Link to the content  |
| `image` | [String](scalar#string) | Icon name for the content  |

## Weather
Weather Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `icon` | [String](scalar#string) | Weather icon to be used  |
| `description` | [String](scalar#string) | Weather description of the description  |
| `temperature` | [[WeatherUnit]](object#weatherunit) | Temperature in both celcius and farenheit  |

## WeatherUnit
Weather Unit Model

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `type` | [String](scalar#string) | Unit Type- Celcius or Farenheit  |
| `value` | [Float](scalar#float) | Current temperature  |

## OutputPreference
Output preference object

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employeeId` | [String](scalar#string) | Employee Id  |
| `key` | [String](scalar#string) | Preferences name  |
| `values` | [[ValueType]](object#valuetype) | Preferences values  |

## ValueType
Preference representation

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Preferred employee id  |
| `type` | [String](scalar#string) | Preference type. Default is string  |
| `timestamp` | [String](scalar#string) | Epoch Timestamp number  |

## PracticeAreaInfo
Practice Area Details

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `Level` | [String](scalar#string) | Level of expertise  |
| `Topic` | [String](scalar#string) | Topic of the practice area  |
| `Type` | [String](scalar#string) | Practice area type  |

## Employees
List of employees for search result with total number of employees actually exists for seach query provided

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](object#employee) | List of employee objects  |
| `totalCount` | [Int](scalar#int) | The total number of matching employees for the search query exists in data base, regardless of limit provided  |
| `searchFilters` | [[SearchResultFilterType]](object#searchresultfiltertype) |   |

## SearchResultFilterType
SearchResultFilter 

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `field` | [String](scalar#string) | FIlter Field Value  |
| `filters` | [[ResultFilterType]](object#resultfiltertype) |    |

## ResultFilterType
ResultFilterType 

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `key` | [String](scalar#string) | FIlter Field Value  |
| `count` | [String](scalar#string) | Longitude of a geo location  |

## JobFunction
Object representation for a Job Function

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](scalar#string) | Name of the Job Function  |

## PracticeArea
Object representation for the Practice Area

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](scalar#string) | Name of the practice area  |
| `category` | [String](scalar#string) | Category of pracitce area  |
| `topics` | [[PracticeAreaTopic]](object#practiceareatopic) | Topics inside practice area  |
| `imageUrl` | [String](scalar#string) | URL of the practice area image  |
| `homeUrl` | [String](scalar#string) | Home Url in practice are  |
| `contentLinks` | [[ContentType]](object#contenttype) | Contents inside the practice area  |

## PracticeAreaTopic
Object representation for the Practice Area Topic

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](scalar#string) | Name of the topic  |

## TeamOutput
Team data

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](scalar#string) | Team Id  |
| `name` | [String](scalar#string) | Team name  |
| `summary` | [String](scalar#string) | Team information summary  |
| `slackURL` | [String](scalar#string) | Team slack URL  |
| `egnyteURL` | [String](scalar#string) | Team egnyte URL  |
| `image` | [String](scalar#string) | Image for the team  |
| `imageName` | [String](scalar#string) | Image for the team  |
| `employeeIds` | [[String]](scalar#string) | Employee Ids of team members  |
| `contentLinks` | [[ContentType]](object#contenttype) | Contents links for team  |

## Topic


| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [ID](scalar#id) | topic id  |
| `name` | [String](scalar#string) | name of topic  |
| `sortOrder` | [String](scalar#string) | sorting preference for UI  |
| `roleCategories` | [[RoleCategory]](object#rolecategory) | categories of role  |

## RoleCategory


| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [ID](scalar#id) | Role category id  |
| `name` | [String](scalar#string) | Name of Role category  |
| `groups` | [[RoleGroup]](object#rolegroup) | Goups of Role  |
| `sortOrder` | [Int](scalar#int) | sorting preference for UI  |

## RoleGroup


| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [ID](scalar#id) | Role group id  |
| `name` | [String](scalar#string) | Name of role group  |
| `sortOrder` | [Int](scalar#int) | sorting preference for UI  |
| `roles` | [[TopicRole]](object#topicrole) | List of roles in current group  |

## TopicRole


| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [ID](scalar#id) | Role id  |
| `name` | [String](scalar#string) | Name of role  |
| `description` | [String](scalar#string) | Description of the role  |
| `displayText` | [String](scalar#string) | Display text for the role  |
| `detailDisplayText` | [String](scalar#string) | Detailed description of role  |
| `contact` | [Employee](object#employee) | Employee details  |
| `sortOrder` | [Int](scalar#int) | sorting preference for UI  |

## PreferncesAPIMutation
Graph based mutation to store an employee's preferences and create teams

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `preference` | [OutputPreference](object#outputpreference) | Add user preferences  |
| `team` | [TeamOutput](object#teamoutput) | Create Team  |
| `deleteTeam` | [TeamOutput](object#teamoutput) | Delete Team  |
| `updateTeam` | [TeamOutput](object#teamoutput) | Update Team  |

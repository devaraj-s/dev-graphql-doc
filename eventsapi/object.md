# Objects

## EventsAPIFetch
Graph based API to get events information, including their location.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `event` | [OutputEvent](object#outputevent) | Fetch event by id  |
| `events` | [[OutputEvent]](object#outputevent) | Fetch events by any filter, such as locationId=LON  |
| `eventsFilter` | [[OutputEvent]](object#outputevent) | Fetch events by any filter, such as locationId=LON  |
| `categories` | [[String]](scalar#string) | Fetch all event categories  |

## OutputEvent
Input event payload

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `title` | [String!](scalar#string) | Title of the event  |
| `_id` | [String](scalar#string) | id of the event  |
| `summary` | [String](scalar#string) | Summary of the event  |
| `timezone` | [String](scalar#string) | Time zone of the event location  |
| `start` | [String](scalar#string) | Start date unix timestamp of the event  |
| `end` | [String](scalar#string) | End date unix timestamp of the event  |
| `locationId` | [String](scalar#string) | Location Id or code of the office  |
| `location` | [OutputLocation](object#outputlocation) | Location details of the office  |
| `hostId` | [String](scalar#string) | Employee Id (HRID) of the host  |
| `host` | [EmployeeOutputType](object#employeeoutputtype) | Host Employee details  |
| `contentLinks` | [[OutputContentType]](object#outputcontenttype) | Events related content links  |
| `attendeesIds` | [[String]](scalar#string) | Employee Ids (HRIDs) of the all the attendees  |
| `attendees` | [[EmployeeOutputType]](object#employeeoutputtype) | Employee details of all the attending employees  |
| `categories` | [[String]](scalar#string) | Category is the type of event. Default is [MEETING]  |
| `category` | [String](scalar#string) | Category is the type of event. Default is MEETING  |
| `categoryImage` | [String](scalar#string) | Category is the type of event. Default is MEETING  |
| `room` | [String](scalar#string) | Room name of venue of the event  |
| `visibility` | [EventVisibility](enum#eventvisibility) | Event visibility scope  |
| `allDay` | [Boolean](scalar#boolean) | Is event for the entire day.  |
| `createdBy` | [String](scalar#string) | Employee Id(HRIDs) of the event creator  |

## OutputLocation
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
| `geoLocation` | [OutputGeoLocation](object#outputgeolocation) | Geolocation has latitude and longitude  |
| `phone` | [String](scalar#string) | Phone number of office  |
| `imageUrl` | [String](scalar#string) | Link to an office image  |
| `contentLinks` | [[OutputContentType]](object#outputcontenttype) | Contents inside the office location  |
| `timezone` | [String](scalar#string) | Time zone of the location  |
| `weather` | [Weather](object#weather) | Current weather for the location  |

## OutputGeoLocation
GeoLocation Type - object for latitude and longitude

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `lat` | [String](scalar#string) | Latitude of a geo location  |
| `lon` | [String](scalar#string) | Longitude of a geo location  |

## OutputContentType
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

## EmployeeOutputType
Employee Type - the main data structure used by the People API graph. In a logical People graph, each node is an instance of this type.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Employee's unique Id.  |
| `name` | [String](scalar#string) | Full name of the Employee with 'Surname, Firstname' format.  |
| `displayName` | [String](scalar#string) | Display name of the Employee with 'Surname Firstname' format.  |
| `firstName` | [String](scalar#string) | Employee's first name.  |
| `lastName` | [String](scalar#string) | Employee's last name.  |
| `title` | [String](scalar#string) | Employee's Business title.  |
| `cohort` | [String](scalar#string) | Employee's cohort  |
| `status` | [String](scalar#string) | Employee's status Active/Inactive/LOA  |
| `jobFunction` | [String](scalar#string) | Employee's job function  |
| `globalTitle` | [String](scalar#string) | Employee's global title  |
| `email` | [String](scalar#string) | Employee's official email.  |
| `phone` | [String](scalar#string) | Employee's official phone.  |
| `mobile` | [String](scalar#string) | Employee's official mobile phone.  |
| `hostOfficeId` | [String](scalar#string) | Employee's host office code, where the employee is currently based  |
| `hostOfficeRegion` | [String](scalar#string) | Host office region  |
| `homeOfficeId` | [String](scalar#string) | Employee's home office code  |
| `homeOfficeRegion` | [String](scalar#string) | Employee's home office region  |
| `location` | [String](scalar#string) | DEPRECATED - location has been deprecated. Use hostLocation { officeCode } or hostOfficeCode instead , Employee's host office location code, where the employee is currently based  |
| `hostOfficeLocation` | [OutputLocation](object#outputlocation) | Employee's host office location object, where the employee is currently based.  |
| `homeOfficeLocation` | [OutputLocation](object#outputlocation) | Employee's home office location object, where the employee is from.  |
| `picture` | [String](scalar#string) | Employee's profile pic in jpeg format.  |
| `profilePicture` | [String](scalar#string) | Employee's profile pic in jpeg format.  |
| `lineManagerId` | [String](scalar#string) | Line Manager's Id.  |
| `lineManager` | [EmployeeOutputType](object#employeeoutputtype) | Line Manager, returned as an Employee object.  |
| `reportingLine` | [[EmployeeOutputType]](object#employeeoutputtype) | Reporting line of the employee. Returned as an array of Employee objects.  |
| `lastUpdated` | [String](scalar#string) | Timestamp when people api updated itself with the snowflake  |

## EventsAPIMutation
Graph based API to get events information, including their location.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `event` | [OutputEvent](object#outputevent) | Create event  |
| `deleteEvent` | [OutputEvent](object#outputevent) | Delete an event with provided _id  |
| `updateEvent` | [OutputEvent](object#outputevent) | Update an event for given _id  |

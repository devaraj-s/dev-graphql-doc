---
layout: default
---
# Objects

## PeopleExternalAPI
Graph based API to get External People information. You can use an Employee query if employee id is known or use a Search query to look up an Employee.<br />

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns multiple employee objects for the array of ids provided.  |
| `employee` | [Employee](object#employee) | Navigate employee graph via this query, you will use this if you have access to Employee ID otherwise use search query. Returns an Employee object.  |
| `peopleSearch` | [Employees](object#employees) | Lookup employee by name, title or any other information you know. Returns an object with list of employees and totalCount.  |
| `searchFilter` | [Employees](object#employees) | Lookup location by name, title or any other information you know. Returns the matching location objects as an array.  |
| `jobFunctions` | [[JobFunction]](object#jobfunction) | Returns list of all distinct job functions  |
| `practiceAreas` | [[PracticeArea]](object#practicearea) | Returns list of all practice area objects  |
| `advancedFilters` | [AdvancedFilters](object#advancedfilters) | Returns list of available advanced filters <br />  |
| `PeopleExternalAPIResponseTime_Oneweektimelinedata` | [[String]](scalar#string) |  <iframe src="https://app.datadoghq.com/graph/embed?token=604d6baee98a8207f465840f9eeef3847bf06fa983bf64be7f6489793fbb61c5&height=200&width=400&legend=true" width="400" height="200" frameborder="0"></iframe>  <iframe src="https://app.datadoghq.com/graph/embed?token=19eddccfe40710a321df48d79919617bdf4d81efbf18402e2d1ac79e9421e009&height=200&width=400&legend=true" width="400" height="200" frameborder="0"></iframe>  |

## Employee
Employee Type - the main data structure used by the People API graph. In a logical People graph, each node is an instance of this type.

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `id` | [String](scalar#string) | Employee's unique Id.  |
| `firstName` | [String](scalar#string) | Employee's first name.  |
| `lastName` | [String](scalar#string) | Employee's last name.  |
| `profilePicture` | [String](scalar#string) | Profile picture  |
| `academicTitle` | [String](scalar#string) | Employee academic title for e.g Dr.  |
| `email` | [String](scalar#string) | Employee's official email.  |
| `phone` | [String](scalar#string) | Employee's official phone.  |
| `jobTitle` | [String](scalar#string) | Employee's job title  |
| `organization` | [String](scalar#string) | Employee's organisation  |
| `assistantName` | [String](scalar#string) | Employee's assistant's name  |
| `assistantEmail` | [String](scalar#string) | Employee's assistant's email  |
| `assistantPhoneNumber` | [String](scalar#string) | Employee's assistant's phone number  |
| `languages` | [[String]](scalar#string) | Languages  |
| `education` | [[Education]](object#education) | Employee's education  |
| `expertiseSummary` | [String](scalar#string) | Employee's expertise  |
| `industryExpertise` | [[String]](scalar#string) | Employee's industry expertise  |
| `functionalExpertise` | [[FunctionalExpertise]](object#functionalexpertise) | Employee's functional expertise  |
| `professionalExperience` | [[ProfessionalBackground]](object#professionalbackground) | List of professional background of employee  |
| `relevantExperience` | [[String]](scalar#string) | Employee's relevant experience  |
| `practiceAreas` | [[PracticeArea]](object#practicearea) | List o practice areas associated with the employee  |
| `lastUpdated` | [String](scalar#string) | Timestamp when people api updated itself with the snowflake  |

## Education
Object representation for the Education

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `degree` | [String](scalar#string) | Degree  |
| `subject` | [String](scalar#string) | Subject  |
| `university` | [String](scalar#string) | University  |
| `years` | [String](scalar#string) | Degree years  |

## FunctionalExpertise
Object representation for the Functional Expertise

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `topic` | [String](scalar#string) | Topic  |
| `level` | [String](scalar#string) | Level of expertise  |

## ProfessionalBackground
Object representation for the Professional Background

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `company` | [String](scalar#string) | Company  |
| `job_title` | [String](scalar#string) | Job title  |
| `industry` | [String](scalar#string) | Industry  |
| `years` | [String](scalar#string) | Years of experience  |

## PracticeArea
Object representation for the Practice Area

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `topic` | [String](scalar#string) | Name/Topic of the practice area  |
| `sub_topic` | [String](scalar#string) | Sub topic of a practice area  |
| `level` | [String](scalar#string) | Level of  expertise of the employee  |

## Employees
List of employees for search result with total number of employees actually exists for seach query provided

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `employees` | [[Employee]](object#employee) | List of employee objects  |
| `totalCount` | [Int](scalar#int) | The total number of matching employees for the search query exists in data base, regardless of limit provided  |

## JobFunction
Object representation for a Job Function

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `name` | [String](scalar#string) | Name of the Job Function  |

## AdvancedFilters
Object for available advanced filters

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `functionalExpertise` | [[String]](scalar#string) | All functional expertise  |
| `practiceAreas` | [[PracticeAreaFilter]](object#practiceareafilter) | All practice areas  |

## PracticeAreaFilter
Object representation for the Practice Area Filter Type

| Field  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `topic` | [String](scalar#string) | Name of the topic  |
| `subTopics` | [[String]](scalar#string) | List of sub topics within a topic  |

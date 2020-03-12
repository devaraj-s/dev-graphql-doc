##"Find" :User wishes to find a person in the employee list
## Sample 1 Request: Find By First Name
```graphql
{
  searchFilter(find:"Vijay Malhan"){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## Sample 1 Response: Find By First Name
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "367929",
                    "name": "Malhan, Vijay",
                    "hostOfficeId": "GSL",
                    "firstName": "Vijay",
                    "lastName": "Malhan",
                    "homeOfficeId": "GSL",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Information Technology",
                    "title": "IT Mobile Applications Senior Lead Architect"
                }
            ],
            "totalCount": 1
        }
    }
}
```
## Sample 2 Request: Find By Job Function
```graphql
{
  searchFilter(find:"Global IT Director"){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## "Filters" :User wants to search for a person in employee list by providing certain filter values
## Sample 1 Request: Multiple search filters used with find and filter Type:OR/NOT
```graphql
{
  searchFilter(find:"Outside Consultant" filters:[{ field:"firstName=Vijay" filterType:NOT}, { field:"lastName=Kolluru" filterType:OR}, { field:"lastName=Arora" filterType:OR}]){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## Sample 1 Response: Multiple search filters used with find and filter Type:OR/NOT
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "...",
                    "name": "Arora, Nidhi",
                    "hostOfficeId": "GSD",
                    "firstName": "Nidhi",
                    "lastName": "Arora",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                },
                {
                    "id": "...",
                    "name": "Arora, Shilpa",
                    "hostOfficeId": "GLB",
                    "firstName": "Shilpa",
                    "lastName": "Arora",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant CresTech"
                },
                {
                    "id": "...",
                    "name": "Arora, Tushar",
                    "hostOfficeId": "GSD",
                    "firstName": "Tushar",
                    "lastName": "Arora",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant Genpact"
                },
                {
                    "id": "...",
                    "name": "Arora, Rishi",
                    "hostOfficeId": "GSD",
                    "firstName": "Rishi",
                    "lastName": "Arora",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant Genpact"
                },
                {
                    "id": "...",
                    "name": "Arora, Rohit",
                    "hostOfficeId": "GSD",
                    "firstName": "Rohit",
                    "lastName": "Arora",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                },
                {
                    "id": "...",
                    "name": "Arora, Avinesh",
                    "hostOfficeId": "GSD",
                    "firstName": "Avinesh",
                    "lastName": "Arora",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant CresTech"
                },
                {
                    "id": "...",
                    "name": "Arora, Kavita",
                    "hostOfficeId": "GSD",
                    "firstName": "Kavita",
                    "lastName": "Arora",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                },
                {
                    "id": "...",
                    "name": "Arora, Saurabh",
                    "hostOfficeId": "GLB",
                    "firstName": "Saurabh",
                    "lastName": "Arora",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant Sapient"
                },
                {
                    "id": "...",
                    "name": "Arora, Samta",
                    "hostOfficeId": "GLB",
                    "firstName": "Samta",
                    "lastName": "Arora",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                },
  ...........
            ],
            "totalCount": 12
        }
    }
}
## Sample 2 Request: Filter by First name and Last name using filterType : AND
```graphql
{
  searchFilter(filters:[{ field:"firstName=Vijay" filterType:AND}, { field:"lastName=Malhan" filterType:AND}]){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## "DataSet" : User wants to search for specific group of people in employee list
## Data-sets Available : BCG_IT , BCG_ALUMINI , BCG_REGULAR , BCG_VENDORS , BCG_ALL
## Sample 1 Request: Search query to filter on First name on dataset BCG_REGULAR
```graphql
{
  searchFilter(filters:[{ field:"firstName=Vijay" filterType:AND}]  dataSet:BCG_REGULAR ){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## Sample 1 Response: Search query to filter on First name on dataset BCG_REGULAR
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "...",
                    "name": "Khokhar, Vijay",
                    "hostOfficeId": "IKA",
                    "firstName": "Vijay",
                    "lastName": "Khokhar",
                    "homeOfficeId": "IKA",
                    "status": "Regular-Active",
                    "globalTitle": "Omnia - Lead Data & Analytics",
                    "jobFunction": "Specialty Level 2",
                    "title": "BCG Omnia - Data & Analytics Lead"
                },
                {
                    "id": "...",
                    "name": "Kathiresan, Vijay",
                    "hostOfficeId": "CHE",
                    "firstName": "Vijay",
                    "lastName": "Kathiresan",
                    "homeOfficeId": "CHE",
                    "status": "Regular-Active",
                    "globalTitle": "Specialist",
                    "jobFunction": "VS Billable",
                    "title": "Designer"
                },
                {
                    "id": "...",
                    "name": "Malhan, Vijay",
                    "hostOfficeId": "GSL",
                    "firstName": "Vijay",
                    "lastName": "Malhan",
                    "homeOfficeId": "GSL",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Information Technology",
                    "title": "IT Mobile Applications Senior Lead Architect"
                },
                {
                    "id": "...",
                    "name": "Chari, Vijay",
                    "hostOfficeId": "MEL",
                    "firstName": "Vijay",
                    "lastName": "Chari",
                    "homeOfficeId": "MEL",
                    "status": "Regular-Active",
                    "globalTitle": "Project Leader",
                    "jobFunction": "Project Leader",
                    "title": "Project Leader"
                },
                {
                    "id": "...",
                    "name": "Thapa, Dig Vijay",
                    "...
                },
                {
                    "id": "...",
                    "name": "Kukreja, Vijay",
                  ...
                },
                {
                    "id": "...",
                    "name": "Patil, Vijay",
                    ....
                }
            ],
            "totalCount": 7
        }
    }
}
```
## Sample 2 Request: Search by firstname and dataset = IT
```graphql
{
  searchFilter(filters:[{ field:"firstName=Vijay" filterType:AND}]  dataSet:BCG_IT ){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## "Pagination" :User wants to see the number of records to display in viewport.This result set should be mutable.Pagination is achievable through limit and offset parameters in People Search
## Sample 1 Request: Filter By First name using dataset and limit=10
```graphql
{
  searchFilter(filters:[{ field:"firstName=Vijay" filterType:AND}]  dataSet:BCG_REGULAR limit: 10 ){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## Sample 1 Response
```graphql 
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "...",
                    "name": "Khokhar, Vijay",
                    "hostOfficeId": "IKA",
                    "firstName": "Vijay",
                    "lastName": "Khokhar",
                    "homeOfficeId": "IKA",
                    "status": "Regular-Active",
                    "globalTitle": "Omnia - Lead Data & Analytics",
                    "jobFunction": "Specialty Level 2",
                    "title": "BCG Omnia - Data & Analytics Lead"
                },
                {
                    "id": "...",
                    "name": "Kathiresan, Vijay",
                    "hostOfficeId": "CHE",
                    "firstName": "Vijay",
                    "lastName": "Kathiresan",
                    "homeOfficeId": "CHE",
                    "status": "Regular-Active",
                    "globalTitle": "Specialist",
                    "jobFunction": "VS Billable",
                    "title": "Designer"
                },
                {
                    "id": "...",
                    "name": "Malhan, Vijay",
                    "hostOfficeId": "GSL",
                    "firstName": "Vijay",
                    "lastName": "Malhan",
                    "homeOfficeId": "GSL",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Information Technology",
                    "title": "IT Mobile Applications Senior Lead Architect"
                },
                {
                    "id": "...",
                    "name": "Chari, Vijay",
                    "hostOfficeId": "MEL",
                    "firstName": "Vijay",
                    "lastName": "Chari",
                    "homeOfficeId": "MEL",
                    "status": "Regular-Active",
                    "globalTitle": "Project Leader",
                    "jobFunction": "Project Leader",
                    "title": "Project Leader"
                },
                {
                    "id": "...",
                    "name": "Thapa, Dig Vijay",
                    "hostOfficeId": "BEK",
                    "firstName": "Dig Vijay",
                    "lastName": "Thapa",
                    "homeOfficeId": "BEK",
                    "status": "Regular-Active",
                    "globalTitle": "Omnia - Junior Technical Delivery",
                    "jobFunction": "Specialty Level 1",
                    "title": "BCG Omnia - Junior Analyst, Solution Support"
                },
                {
                    "id": "...",
                    "name": "Kukreja, Vijay",
                    "hostOfficeId": "TOR",
                    "firstName": "Vijay",
                    "lastName": "Kukreja",
                    "homeOfficeId": "TOR",
                    "status": "Regular-Active",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                },
                {
                    "id": "...",
                    "name": "Patil, Vijay",
                    "hostOfficeId": "BEK",
                    "firstName": "Vijay",
                    "lastName": "Patil",
                    "homeOfficeId": "BEK",
                    "status": "Regular-Active",
                    "globalTitle": "Knowledge Analyst",
                    "jobFunction": "Knowledge Team",
                    "title": "Analyst - GAMMA"
                }
            ],
            "totalCount": 7
        }
    }
}
```
## "Sorting" :User wants to get the response in a sequential order
## Sample 1 Request : Filter by First name and Sort By Last name - default Ascending sort
```graphql
{
  searchFilter(filters:[{ field:"firstName=Vijay" filterType:AND}]  dataSet:BCG_REGULAR limit: 10 offset:5 sortBy:"lastName"){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## Sample 1 Response  : Filter by First name and Sort By Last name - default Ascending sort
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "...",
                    "name": "Patil, Vijay",
                    "hostOfficeId": "BEK",
                    "firstName": "Vijay",
                    "lastName": "Patil",
                    "homeOfficeId": "BEK",
                    "status": "Regular-Active",
                    "globalTitle": "Knowledge Analyst",
                    "jobFunction": "Knowledge Team",
                    "title": "Analyst - GAMMA"
                },
                {
                    "id": "...",
                    "name": "Thapa, Dig Vijay",
                    "hostOfficeId": "BEK",
                    "firstName": "Dig Vijay",
                    "lastName": "Thapa",
                    "homeOfficeId": "BEK",
                    "status": "Regular-Active",
                    "globalTitle": "Omnia - Junior Technical Delivery",
                    "jobFunction": "Specialty Level 1",
                    "title": "BCG Omnia - Junior Analyst, Solution Support"
                }
            ],
            "totalCount": 7
        }
    }
}
```
## Sample 3 Request : Sort By First name in ascending order
```graphql
{
  searchFilter(filters:[{ field:"firstName=Vijay" filterType:AND}]  dataSet:BCG_ALL sortBy:"firstName" sortOrder:ASC){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## Sample 4 Request : Multiple - Sort By First name and Last name in ascending order
```graphql
{
  searchFilter(filters:[{ field:"firstName=Vijay" filterType:AND}]  dataSet:BCG_ALL sortBy:["firstName","lastName"] sortOrder:ASC limit: 5 offset:0){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## Sample 4 Response : multiple sorting
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "359819",
                    "name": "Thapa, Dig Vijay",
                    "hostOfficeId": "BEK",
                    "firstName": "Dig Vijay",
                    "lastName": "Thapa",
                    "homeOfficeId": "BEK",
                    "status": "Regular-Active",
                    "globalTitle": "Omnia - Junior Technical Delivery",
                    "jobFunction": "Specialty Level 1",
                    "title": "BCG Omnia - Junior Analyst, Solution Support"
                },
                {
                    "id": "297462",
                    "name": "Agashe, Vijay",
                    ...
                },
                {
                    "id": "347892",
                    "name": "Arora, Vijay",
                    ....
                },
                {
                    "id": "341031",
                    "name": "Chandran, Vijay",
                    ....
                },
                {
                    "id": "253352",
                    "name": "Chandrathil, Vijay",
                    ....
                }
            ],
            "totalCount": 28
        }
    }
}
```
## Fuzzy Search : A fuzzy matching program operates like a spell checker and spelling-error corrector.
## Sample 1 Request : First name and Last name both have spelling mistakes
```graphql
{
    searchFilter( find:"vijy mahlan" sortBy:"firstName" ){
      employees{
        id
        name
        hostOfficeId
        firstName
        lastName
        homeOfficeId
        status
        globalTitle
        jobFunction
        status
        title
      }
       
    }
 }
```
## Sample 1 Response : First name and Last name both have spelling mistakes
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "367929",
                    "name": "Malhan, Vijay",
                    "hostOfficeId": "GSL",
                    "firstName": "Vijay",
                    "lastName": "Malhan",
                    "homeOfficeId": "GSL",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Information Technology",
                    "title": "IT Mobile Applications Senior Lead Architect"
                }
            ]
        }
    }
}
```
## Type-Ahead Search -  People API also supports Auto-complete feature.  Sort By can be used as well on specific fields.
## Sample 1 Request : Type Ahead Search with Location Filter and DataSet
```graphql
{
  searchFilter( find:"vi"   filters:[{field:"homeOfficeId=GSL" filterType:AND}] sortBy:"name"  dataSet:BCG_REGULAR){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
     
  }
}
```
## Sample 1 Response : Type Ahead Search with Location Filter and DataSet
```graphql
{
  "data": {
    "searchFilter": {
      "employees": [
        {
          "id": "367929",
          "name": "Malhan, Vijay",
          "hostOfficeId": "GSL",
          "firstName": "Vijay",
          "lastName": "Malhan",
          "homeOfficeId": "GSL",
          "status": "Regular-Active",
          "globalTitle": "Senior Manager",
          "jobFunction": "Information Technology",
          "title": "IT Mobile Applications Senior Lead Architect"
        },
{
          "id": "372138",
          "name": "Vielle, Jennifer",
          "hostOfficeId": "GSL",
          "firstName": "Jennifer",
          "lastName": "Vielle",
          "homeOfficeId": "GSL",
          "status": "Regular-Active",
          "globalTitle": "Lead",
          "jobFunction": "Operations",
          "title": "Sourcing Lead - Facilities Management"
        }
      ]
    }
  }
}
```
## Search with Single Character
## Sample 1 Request : Filter by Last Name with single char
```graphql
query {
    searchFilter(find:"", filters:[{field: "firstName=H*", filterType: AND} {field: "lastName=G*", filterType: AND}] sortBy:"lastName" ) {
    totalCount
    employees {
      id
      firstName
      lastName
    }
  }
}
```
## Response : Sorted response by Lastname in ascending order
```graphql
{
    "data": {
        "searchFilter": {
            "totalCount": 9,
            "employees": [
                {
                    "id": "353217",
                    "firstName": "Hossam",
                    "lastName": "Gabri"
                },
                {
                    "id": "377593",
                    "firstName": "Hillie",
                    "lastName": "Gaither"
                },
                {
                    "id": "337144",
                    "firstName": "Hector",
                    "lastName": "George"
                },
                {
                    "id": "344400",
                    "firstName": "Harry",
                    "lastName": "Green"
                },
                {
                    "id": "129012",
                    "firstName": "Helge",
                    "lastName": "Groß"
                },
                {
                    "id": "88332",
                    "firstName": "Hongzhou",
                    "lastName": "Guo"
                },
                {
                    "id": "389542",
                    "firstName": "Harshit",
                    "lastName": "Gupta"
                },
                {
                    "id": "330330",
                    "firstName": "Himanshu",
                    "lastName": "Gupta"
                },
                {
                    "id": "376314",
                    "firstName": "Himank",
                    "lastName": "Gupta"
                }
            ]
        }
    }
}
```
## Aggregation - resultFilter - Used for Aggregation / Grouping the fields specified in search query.Multiple or single filter can be used in single query.
## Sample 1 request : Filter by First Name and Group By job function
```graphql
{
  searchFilter(filters:[{ field:"firstName=Vijay" filterType:AND}]  resultFilters:["jobFunction"] dataSet:BCG_ALL limit: 5 offset:0 sortBy:"title" ){
    employees{
      id
      name
      hostOfficeId
      firstName
      lastName
      homeOfficeId
      status
      globalTitle
      jobFunction
      status
      title
    }
    totalCount
  }
}
```
## Sample 1 response :
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "...",
                    "name": "Iyer, Vijay",
                    "hostOfficeId": "CHI",
                    "firstName": "Vijay",
                    "lastName": "Iyer",
                    "homeOfficeId": "CHI",
                    "status": "Regular-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Knowledge Team Billable",
                    "title": "Analyst"
                },
                {
                    "id": "...",
                    "name": "Patil, Vijay",
                    "hostOfficeId": "BEK",
                    "firstName": "Vijay",
                    "lastName": "Patil",
                    "homeOfficeId": "BEK",
                    "status": "Regular-Active",
                    "globalTitle": "Knowledge Analyst",
                    "jobFunction": "Knowledge Team",
                    "title": "Analyst - GAMMA"
                },
                {
                    "id": "...",
                    "name": "Khokhar, Vijay",
                    "hostOfficeId": "IKA",
                    "firstName": "Vijay",
                    "lastName": "Khokhar",
                    "homeOfficeId": "IKA",
                    "status": "Regular-Active",
                    "globalTitle": "Omnia - Lead Data & Analytics",
                    "jobFunction": "Specialty Level 2",
                    "title": "BCG Omnia - Data & Analytics Lead"
                },
                {
                    "id": "...",
                    "name": "Thapa, Dig Vijay",
                    "hostOfficeId": "BEK",
                    "firstName": "Dig Vijay",
                    "lastName": "Thapa",
                    "homeOfficeId": "BEK",
                    "status": "Regular-Active",
                    "globalTitle": "Omnia - Junior Technical Delivery",
                    "jobFunction": "Specialty Level 1",
                    "title": "BCG Omnia - Junior Analyst, Solution Support"
                },
                {
                    "id": "...",
                    "name": "Singh, Vijay",
                    "hostOfficeId": "WAS",
                    "firstName": "Vijay",
                    "lastName": "Singh",
                    "homeOfficeId": "WAS",
                    "status": "Regular-Terminated",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                }
            ],
            "totalCount": 28
        }
    }
}
```
## Sample 2 request : Aggregation along with Nested filter fields
```graphql
{
  searchFilter( find:"director"  resultFilters:["hostOfficeId"]   ){
    employees{
      id
      name
      lastName
      title
      status
      hostOfficeId
    }
    searchFilters{
        field
        filters{
            key
            count
        }
    }
    totalCount
  }
}
```
## Sample 2 Response - Nested filters with Aggregation
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "8872",
                    "name": "Aham, Tom",
                    "lastName": "Aham",
                    "title": "Global IT Director - Technology Operations Meetings & Offices",
                    "status": "Regular-Active",
                    "hostOfficeId": "GSB"
                },
                {
                    "id": "381299",
                    "name": "DiVittorio, Paul",
                    "lastName": "DiVittorio",
                    "title": "Global IT Director - Cloud Infrastructure",
                    "status": "Regular-Active",
                    "hostOfficeId": "GSB"
                },
.......
 
                            "key": "BKA",
                            "count": "2"
                        },
                        {
                            "key": "DUS",
                            "count": "2"
                        },
                        {
                            "key": "NXA",
                            "count": "2"
                        }
                    ]
                }
            ],
            "totalCount": 72
        }
    }
}
```  

<iframe src="https://www.site24x7.eu/public/dashboard/FBlvh5-GIjZQ09kmJ05p1Fwf7Ra0mG2BSCYyMVfmq2alBW5Tkx55s7bPHfqIzxvLEOtJnC8lr8dQtZG5e-rGOAuhQYjGHWTH4izoFkhk3JTrq3xlVKIiynzbPbiIhati" scrolling="yes" align="center" height="400" width="1200" border="0" frameborder="0"></iframe>
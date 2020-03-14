## "Find" :User wishes to find a person in the employee list
## Sample 1 Request: Find By First Name
```graphql
{
  searchFilter(find:"Sharia Blennerhassett"){
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
      lineManager{ name title picture } 
      reportingLine {id  name title picture}
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
                    "name": "Sharia Blennerhassett",
                    "hostOfficeId": "GSL",
                    "firstName": "Sharia",
                    "lastName": "Blennerhassett",
                    "homeOfficeId": "GSL",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Information Technology",
                    "title": "IT Mobile Applications Senior Lead Architect",
                    "lineManager": {
                        "name": "Austine Hayler",
                        "title": "Global IT Director - Business Systems Product Engineering & Technology",
                        "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=340862"
                    },
                    "reportingLine": [
                        {
                            "id": "389755",
                            "name": "Karl Sides",
                            "title": "Outside Consultant - BST",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=389755"
                        },
                        {
                            "id": "389754",
                            "name": "Raquela Eacle",
                            "title": "Outside Consultant - BST",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=389754"
                        },
                        {
                            "id": "378299",
                            "name": "Jillana Markos",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=378299"
                        },
                        {
                            "id": "377984",
                            "name": "Angelita Simonot",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=377984"
                        },
                        {
                            "id": "384365",
                            "name": "Fonsie Mingey",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=384365"
                        },
                        {
                            "id": "360347",
                            "name": "Aimil Larkcum",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=360347"
                        },
                        {
                            "id": "388986",
                            "name": "Geoffrey Cochran",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=388986"
                        },
                        {
                            "id": "379649",
                            "name": "Roch Hanaford",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=379649"
                        },
                        {
                            "id": "381857",
                            "name": "Dede MacAscaidh",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=381857"
                        },
                        {
                            "id": "384349",
                            "name": "Dynah Mallison",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=384349"
                        },
                        {
                            "id": "360711",
                            "name": "Chalmers Rutley",
                            "title": "IT Mobile Application Architect II",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=360711"
                        },
                        {
                            "id": "389308",
                            "name": "Mirilla Jinda",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=389308"
                        },
                        {
                            "id": "380753",
                            "name": "Den Batrick",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=380753"
                        },
                        {
                            "id": "378300",
                            "name": "Ag Creak",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=378300"
                        },
                        {
                            "id": "361544",
                            "name": "Venus Feaveer",
                            "title": "IT Program Senior Manager",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=361544"
                        },
                        {
                            "id": "381187",
                            "name": "Bartram Bareham",
                            "title": "Outside Consultant",
                            "picture": "http://staffpicture.bcg.com/staffpicture/Default.aspx?hrid=381187"
                        }
                    ]
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
  searchFilter(find:"Outside Consultant" filters:[{ field:"firstName=Sharia" filterType:NOT}, { field:"lastName=Creak" filterType:OR}, { field:"lastName=Hanaford" filterType:OR}]){
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
                    "id": "379649",
                    "name": "Roch Hanaford",
                    "hostOfficeId": "GSD",
                    "firstName": "Roch",
                    "lastName": "Hanaford",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                },
                {
                    "id": "322146",
                    "name": "Berny Hanaford",
                    "hostOfficeId": "GLB",
                    "firstName": "Berny",
                    "lastName": "Hanaford",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant WIPRO"
                },
                {
                    "id": "378300",
                    "name": "Ag Creak",
                    "hostOfficeId": "GSD",
                    "firstName": "Ag",
                    "lastName": "Creak",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                }
            ],
            "totalCount": 3
        }
    }
}
```
## Sample 2 Request: Filter by First name and Last name using filterType : AND
```graphql
{
  searchFilter(filters:[{ field:"firstName=Sharia" filterType:AND}, { field:"lastName=Blennerhassett" filterType:AND}]){
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
## Sample 2 Response: Filter by First name and Last name using filterType : AND
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "367929",
                    "name": "Blennerhassett, Sharia",
                    "hostOfficeId": "GSL",
                    "firstName": "Sharia",
                    "lastName": "Blennerhassett",
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
## "DataSet" : User wants to search for specific group of people in employee list
## Data-sets Available : BCG_IT , BCG_ALUMINI , BCG_REGULAR , BCG_VENDORS , BCG_ALL
## Sample 1 Request: Search query to filter on First name on dataset BCG_REGULAR
```graphql
{
  searchFilter(filters:[{ field:"firstName=Sharia" filterType:AND}]  dataSet:BCG_REGULAR ){
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
                    "id": "227312",
                    "name": "Sharia Puddifer",
                    "hostOfficeId": "MOS",
                    "firstName": "Sharia",
                    "lastName": "Puddifer",
                    "homeOfficeId": "OOO",
                    "status": "Regular-Active",
                    "globalTitle": "Project Leader",
                    "jobFunction": "Project Leader",
                    "title": "Project Leader"
                },
                {
                    "id": "367929",
                    "name": "Sharia Blennerhassett",
                    "hostOfficeId": "GSL",
                    "firstName": "Sharia",
                    "lastName": "Blennerhassett",
                    "homeOfficeId": "GSL",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Information Technology",
                    "title": "IT Mobile Applications Senior Lead Architect"
                },
                {
                    "id": "177514",
                    "name": "Sharia Leythley",
                    "hostOfficeId": "MUM",
                    "firstName": "Sharia",
                    "lastName": "Leythley",
                    "homeOfficeId": "MUM",
                    "status": "Regular-Active",
                    "globalTitle": "Managing Director and Partner",
                    "jobFunction": "MD and Partner",
                    "title": "Managing Director and Partner"
                }
            ],
            "totalCount": 3
        }
    }
}
```
## Sample 2 Request: Search by firstname and dataset = IT
```graphql
{
  searchFilter(filters:[{ field:"firstName=Sharia" filterType:AND}]  dataSet:BCG_IT ){
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
## Sample 1 Request: Find By First name using dataset and limit=10
```graphql
{
    searchFilter( find:"crek" dataSet:BCG_REGULAR sortBy:"name" limit:10 offset:2){
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
## Sample 1 Response
```graphql 
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "310123",
                    "name": "Elita Creelman",
                    "hostOfficeId": "WAS",
                    "firstName": "Elita",
                    "lastName": "Creelman",
                    "homeOfficeId": "WAS",
                    "status": "Regular-Active",
                    "globalTitle": "Principal",
                    "jobFunction": "Sr Consulting Team",
                    "title": "Principal"
                },
                {
                    "id": "196695",
                    "name": "Gerry Flude",
                    "hostOfficeId": "CHI",
                    "firstName": "Gerry",
                    "lastName": "Flude",
                    "homeOfficeId": "CHI",
                    "status": "Regular-Active",
                    "globalTitle": "Manager",
                    "jobFunction": "Human Resources",
                    "title": "Talent Acquisition Manager Analytics Screening & Selection"
                },
                {
                    "id": "352175",
                    "name": "Gretel Screech",
                    "hostOfficeId": "SGO",
                    "firstName": "Gretel",
                    "lastName": "Screech",
                    "homeOfficeId": "SGO",
                    "status": "Regular-Active",
                    "globalTitle": "Project Leader",
                    "jobFunction": "Project Leader",
                    "title": "Project Leader"
                },
                {
                    "id": "361449",
                    "name": "Hastie McCree",
                    "hostOfficeId": "LON",
                    "firstName": "Hastie",
                    "lastName": "McCree",
                    "homeOfficeId": "LON",
                    "status": "Regular-Active",
                    "globalTitle": "Accountant",
                    "jobFunction": "Finance",
                    "title": "Financial Accountant"
                },
                {
                    "id": "374813",
                    "name": "Jackqueline Cree",
                    "hostOfficeId": "NJY",
                    "firstName": "Jackqueline",
                    "lastName": "Cree",
                    "homeOfficeId": "NJY",
                    "status": "Regular-Active",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                },
                {
                    "id": "14076",
                    "name": "Kliment Creeboe",
                    "hostOfficeId": "SIN",
                    "firstName": "Kliment",
                    "lastName": "Creeboe",
                    "homeOfficeId": "SIN",
                    "status": "Regular-Active",
                    "globalTitle": "Managing Director and Senior Partner",
                    "jobFunction": "MD and Partner",
                    "title": "Managing Director and Senior Partner"
                },
                {
                    "id": "354963",
                    "name": "Marja McCreery",
                    "hostOfficeId": "KLP",
                    "firstName": "Marja",
                    "lastName": "McCreery",
                    "homeOfficeId": "KLP",
                    "status": "Regular-Active",
                    "globalTitle": "Project Leader",
                    "jobFunction": "Project Leader",
                    "title": "Project Leader"
                },
                {
                    "id": "903",
                    "name": "Skye Creech",
                    "hostOfficeId": "CHI",
                    "firstName": "Skye",
                    "lastName": "Creech",
                    "homeOfficeId": "GLB",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Human Resources",
                    "title": "Digital and ABM Women at BCG Senior Manager"
                },
                {
                    "id": "344632",
                    "name": "Terrill Creer",
                    "hostOfficeId": "LON",
                    "firstName": "Terrill",
                    "lastName": "Creer",
                    "homeOfficeId": "LON",
                    "status": "Regular-LOA",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                },
                {
                    "id": "352071",
                    "name": "Thaddus Creech",
                    "hostOfficeId": "MUN",
                    "firstName": "Thaddus",
                    "lastName": "Creech",
                    "homeOfficeId": "MUN",
                    "status": "Regular-Active",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                }
            ]
        }
    }
}
```
## "Sorting" :User wants to get the response in a sequential order
## Sample 1 Request : Filter by First name and Sort By Last name - default Ascending sort
```graphql
{
  searchFilter(filters:[{ field:"firstName=Sharia" filterType:AND}]  dataSet:BCG_ALL sortBy:["lastName"] sortOrder:DESC){
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
                    "id": "3818",
                    "name": "Sharia Zammett",
                    "hostOfficeId": "CHI",
                    "firstName": "Sharia",
                    "lastName": "Zammett",
                    "homeOfficeId": "CHI",
                    "status": "Regular-Terminated",
                    "globalTitle": "Reception",
                    "jobFunction": "Operations",
                    "title": "Anonymized Business Title"
                },
                {
                    "id": "266162",
                    "name": "Sharia Troutbeck",
                    "hostOfficeId": "MEX",
                    "firstName": "Sharia",
                    "lastName": "Troutbeck",
                    "homeOfficeId": "MEX",
                    "status": "Regular-Terminated",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                },
                {
                    "id": "227312",
                    "name": "Sharia Puddifer",
                    "hostOfficeId": "MOS",
                    "firstName": "Sharia",
                    "lastName": "Puddifer",
                    "homeOfficeId": "OOO",
                    "status": "Regular-Active",
                    "globalTitle": "Project Leader",
                    "jobFunction": "Project Leader",
                    "title": "Project Leader"
                },
                {
                    "id": "340654",
                    "name": "Sharia Pedder",
                    "hostOfficeId": "DST",
                    "firstName": "Sharia",
                    "lastName": "Pedder",
                    "homeOfficeId": "DST",
                    "status": "Temporary-Terminated",
                    "globalTitle": "Assistant",
                    "jobFunction": "Human Resources",
                    "title": "Temporary Employee"
                },
                {
                    "id": "171377",
                    "name": "Sharia Nickell",
                    "hostOfficeId": "DAL",
                    "firstName": "Sharia",
                    "lastName": "Nickell",
                    "homeOfficeId": "DAL",
                    "status": "Regular-Terminated",
                    "globalTitle": "Associate",
                    "jobFunction": "Associate",
                    "title": "Associate"
                },
                {
                    "id": "177514",
                    "name": "Sharia Leythley",
                    "hostOfficeId": "MUM",
                    "firstName": "Sharia",
                    "lastName": "Leythley",
                    "homeOfficeId": "MUM",
                    "status": "Regular-Active",
                    "globalTitle": "Managing Director and Partner",
                    "jobFunction": "MD and Partner",
                    "title": "Managing Director and Partner"
                },
                {
                    "id": "387614",
                    "name": "Sharia Labdon",
                    "hostOfficeId": "GSD",
                    "firstName": "Sharia",
                    "lastName": "Labdon",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant Genpact"
                },
                {
                    "id": "12733",
                    "name": "Sharia Cuttle",
                    "hostOfficeId": "SIN",
                    "firstName": "Sharia",
                    "lastName": "Cuttle",
                    "homeOfficeId": "SIN",
                    "status": "Regular-Terminated",
                    "globalTitle": "Managing Director and Partner",
                    "jobFunction": "MD and Partner",
                    "title": "Anonymized Business Title"
                },
                {
                    "id": "349105",
                    "name": "Sharia Cullum",
                    "hostOfficeId": "Unknown",
                    "firstName": "Sharia",
                    "lastName": "Cullum",
                    "homeOfficeId": "Unknown",
                    "status": "NULL",
                    "globalTitle": "Unknown",
                    "jobFunction": "Unknown",
                    "title": "NULL"
                },
                {
                    "id": "185552",
                    "name": "Sharia Corser",
                    "hostOfficeId": "AMS",
                    "firstName": "Sharia",
                    "lastName": "Corser",
                    "homeOfficeId": "AMS",
                    "status": "Contract-Terminated",
                    "globalTitle": "Reception",
                    "jobFunction": "Operations",
                    "title": "Reception"
                },
                {
                    "id": "367929",
                    "name": "Sharia Blennerhassett",
                    "hostOfficeId": "GSL",
                    "firstName": "Sharia",
                    "lastName": "Blennerhassett",
                    "homeOfficeId": "GSL",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Information Technology",
                    "title": "IT Mobile Applications Senior Lead Architect"
                },
                {
                    "id": "255217",
                    "name": "Sharia Allison",
                    "hostOfficeId": "TOK",
                    "firstName": "Sharia",
                    "lastName": "Allison",
                    "homeOfficeId": "TOK",
                    "status": "Regular-Terminated",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                }
            ],
            "totalCount": 12
        }
    }
}
```
## Sample 3 Request : Sort By First name in ascending order
```graphql
{
  searchFilter(filters:[{ field:"firstName=Sharia" filterType:AND}]  dataSet:BCG_ALL sortBy:"firstName" sortOrder:ASC){
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
  searchFilter(filters:[{ field:"firstName=Sharia" filterType:AND}]  dataSet:BCG_ALL sortBy:["firstName","title"] sortOrder:ASC limit: 5 offset:0){
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
                    "id": "3818",
                    "name": "Sharia Zammett",
                    "hostOfficeId": "CHI",
                    "firstName": "Sharia",
                    "lastName": "Zammett",
                    "homeOfficeId": "CHI",
                    "status": "Regular-Terminated",
                    "globalTitle": "Reception",
                    "jobFunction": "Operations",
                    "title": "Anonymized Business Title"
                },
                {
                    "id": "12733",
                    "name": "Sharia Cuttle",
                    "hostOfficeId": "SIN",
                    "firstName": "Sharia",
                    "lastName": "Cuttle",
                    "homeOfficeId": "SIN",
                    "status": "Regular-Terminated",
                    "globalTitle": "Managing Director and Partner",
                    "jobFunction": "MD and Partner",
                    "title": "Anonymized Business Title"
                },
                {
                    "id": "171377",
                    "name": "Sharia Nickell",
                    "hostOfficeId": "DAL",
                    "firstName": "Sharia",
                    "lastName": "Nickell",
                    "homeOfficeId": "DAL",
                    "status": "Regular-Terminated",
                    "globalTitle": "Associate",
                    "jobFunction": "Associate",
                    "title": "Associate"
                },
                {
                    "id": "255217",
                    "name": "Sharia Allison",
                    "hostOfficeId": "TOK",
                    "firstName": "Sharia",
                    "lastName": "Allison",
                    "homeOfficeId": "TOK",
                    "status": "Regular-Terminated",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                },
                {
                    "id": "266162",
                    "name": "Sharia Troutbeck",
                    "hostOfficeId": "MEX",
                    "firstName": "Sharia",
                    "lastName": "Troutbeck",
                    "homeOfficeId": "MEX",
                    "status": "Regular-Terminated",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                }
            ],
            "totalCount": 12
        }
    }
}
```
## Fuzzy Search : A fuzzy matching program operates like a spell checker and spelling-error corrector.
## Sample 1 Request : Last name has spelling mistakes
```graphql
{
    searchFilter( find:"Hardy Giblet" sortBy:"firstName" ){
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
## Sample 1 Response : First name and Last name both have spelling mistakes
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "2431",
                    "name": "Hardy Giblett",
                    "hostOfficeId": "LON",
                    "firstName": "Hardy",
                    "lastName": "Giblett",
                    "homeOfficeId": "LON",
                    "status": "Temporary-Terminated",
                    "globalTitle": "Support Leader",
                    "jobFunction": "Information Technology",
                    "title": "Anonymized Business Title"
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
    searchFilter( find:"Shar" sortBy:"name"){
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
## Sample 1 Response : Type Ahead Search with Location Filter and DataSet
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "51051",
                    "name": "Concordia Sharville",
                    "hostOfficeId": "PCL",
                    "firstName": "Concordia",
                    "lastName": "Sharville",
                    "homeOfficeId": "PCL",
                    "status": "Regular-Terminated",
                    "globalTitle": "Architect",
                    "jobFunction": "Information Technology",
                    "title": "Anonymized Business Title"
                },
                {
                    "id": "37007",
                    "name": "Constanta Sharrard",
                    "hostOfficeId": "SEO",
                    "firstName": "Constanta",
                    "lastName": "Sharrard",
                    "homeOfficeId": "SEO",
                    "status": "Regular-Terminated",
                    "globalTitle": "Assistant",
                    "jobFunction": "Information Technology",
                    "title": "Anonymized Business Title"
                },
                {
                    "id": "352889",
                    "name": "Fredric Sharvell",
                    "hostOfficeId": "NYC",
                    "firstName": "Fredric",
                    "lastName": "Sharvell",
                    "homeOfficeId": "NYC",
                    "status": "Temporary-Terminated",
                    "globalTitle": "Assistant",
                    "jobFunction": "Information Technology",
                    "title": "Temporary Employee"
                },
                {
                    "id": "175112",
                    "name": "Louise Sharland",
                    "hostOfficeId": "HOU",
                    "firstName": "Louise",
                    "lastName": "Sharland",
                    "homeOfficeId": "HOU",
                    "status": "Regular-Terminated",
                    "globalTitle": "Specialist",
                    "jobFunction": "Information Technology",
                    "title": "Senior IT Specialist"
                },
                {
                    "id": "335907",
                    "name": "Mela Sharman",
                    "hostOfficeId": "GLB",
                    "firstName": "Mela",
                    "lastName": "Sharman",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                },
                {
                    "id": "367929",
                    "name": "Sharia Blennerhassett",
                    "hostOfficeId": "GSL",
                    "firstName": "Sharia",
                    "lastName": "Blennerhassett",
                    "homeOfficeId": "GSL",
                    "status": "Regular-Active",
                    "globalTitle": "Senior Manager",
                    "jobFunction": "Information Technology",
                    "title": "IT Mobile Applications Senior Lead Architect"
                },
                {
                    "id": "387614",
                    "name": "Sharia Labdon",
                    "hostOfficeId": "GSD",
                    "firstName": "Sharia",
                    "lastName": "Labdon",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant Genpact"
                },
                {
                    "id": "344572",
                    "name": "Sharity Durnford",
                    "hostOfficeId": "GLB",
                    "firstName": "Sharity",
                    "lastName": "Durnford",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                },
                {
                    "id": "345167",
                    "name": "Sharl Bristowe",
                    "hostOfficeId": "GSB",
                    "firstName": "Sharl",
                    "lastName": "Bristowe",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Service Center - IT Specialist"
                },
                {
                    "id": "380225",
                    "name": "Sharla Clouter",
                    "hostOfficeId": "GSL",
                    "firstName": "Sharla",
                    "lastName": "Clouter",
                    "homeOfficeId": "GSL",
                    "status": "Temporary-Terminated",
                    "globalTitle": "Assistant",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant - BST"
                },
                {
                    "id": "387753",
                    "name": "Sharlene Morhall",
                    "hostOfficeId": "GSD",
                    "firstName": "Sharlene",
                    "lastName": "Morhall",
                    "homeOfficeId": "GSD",
                    "status": "Contract-Active",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant CresTech"
                },
                {
                    "id": "359527",
                    "name": "Sharline Nottle",
                    "hostOfficeId": "MIL",
                    "firstName": "Sharline",
                    "lastName": "Nottle",
                    "homeOfficeId": "MIL",
                    "status": "Regular-Active",
                    "globalTitle": "Specialist",
                    "jobFunction": "Information Technology",
                    "title": "IT Specialist"
                },
                {
                    "id": "312262",
                    "name": "Sharon Gutridge",
                    "hostOfficeId": "MUN",
                    "firstName": "Sharon",
                    "lastName": "Gutridge",
                    "homeOfficeId": "GSV",
                    "status": "Temporary-Terminated",
                    "globalTitle": "Trainee",
                    "jobFunction": "Information Technology",
                    "title": "Student"
                },
                {
                    "id": "239373",
                    "name": "Sharyl Eppson",
                    "hostOfficeId": "GLB",
                    "firstName": "Sharyl",
                    "lastName": "Eppson",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant"
                },
                {
                    "id": "349891",
                    "name": "Timi Sharphurst",
                    "hostOfficeId": "GLB",
                    "firstName": "Timi",
                    "lastName": "Sharphurst",
                    "homeOfficeId": "GLB",
                    "status": "Contract-Terminated",
                    "globalTitle": "Analyst",
                    "jobFunction": "Information Technology",
                    "title": "Outside Consultant Sapient"
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
            "totalCount": 15,
            "employees": [
                {
                    "id": "369697",
                    "firstName": "Harald",
                    "lastName": "Gasquoine"
                },
                {
                    "id": "385328",
                    "firstName": "Heloise",
                    "lastName": "Geekin"
                },
                {
                    "id": "67392",
                    "firstName": "Horatius",
                    "lastName": "Geroldi"
                },
                {
                    "id": "3070",
                    "firstName": "Hercules",
                    "lastName": "Gherardesci"
                },
                {
                    "id": "2431",
                    "firstName": "Hardy",
                    "lastName": "Giblett"
                },
                {
                    "id": "342269",
                    "firstName": "Hayward",
                    "lastName": "Gillise"
                },
                {
                    "id": "105133",
                    "firstName": "Heinrick",
                    "lastName": "Glaisner"
                },
                {
                    "id": "385520",
                    "firstName": "Hildagarde",
                    "lastName": "Gooden"
                },
                {
                    "id": "384887",
                    "firstName": "Harald",
                    "lastName": "Goodnow"
                },
                {
                    "id": "355894",
                    "firstName": "Hansiain",
                    "lastName": "Greatbach"
                },
                {
                    "id": "60052",
                    "firstName": "Hali",
                    "lastName": "Greenshiels"
                },
                {
                    "id": "350594",
                    "firstName": "Harbert",
                    "lastName": "Grevile"
                },
                {
                    "id": "350396",
                    "firstName": "Harald",
                    "lastName": "Grindlay"
                },
                {
                    "id": "313962",
                    "firstName": "Hershel",
                    "lastName": "Grishmanov"
                },
                {
                    "id": "354505",
                    "firstName": "Humberto",
                    "lastName": "Gundrey"
                }
            ]
        }
    }
}
```
## Aggregation - resultFilter - Used for Aggregation / Grouping the fields specified in search query.Multiple or single filter can be used in single query.
## Sample 1 request : Filter by First Name and Group By job function along with Nested filter fields
```graphql
{
  searchFilter( find:"IT Mobile Applications Senior Lead Architect"  resultFilters:["hostOfficeId"]   ){
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
## Sample 1 response :
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "367929",
                    "name": "Sharia Blennerhassett",
                    "lastName": "Blennerhassett",
                    "title": "IT Mobile Applications Senior Lead Architect",
                    "status": "Regular-Active",
                    "hostOfficeId": "GSL"
                }
            ],
            "searchFilters": [
                {
                    "field": "hostOfficeId",
                    "filters": [
                        {
                            "key": "GSL",
                            "count": "1"
                        }
                    ]
                }
            ],
            "totalCount": 1
        }
    }
}
```
## Sample 2 request : Aggregation on field jobFunction without nested query
```graphql
{
  searchFilter(filters:[{ field:"firstName=Sharia" filterType:AND}]  resultFilters:["jobFunction"] dataSet:BCG_ALL limit: 5 offset:0 sortBy:["title"] ){
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
## Sample 2 Response - Nested filters with Aggregation
```graphql
{
    "data": {
        "searchFilter": {
            "employees": [
                {
                    "id": "3818",
                    "name": "Sharia Zammett",
                    "hostOfficeId": "CHI",
                    "firstName": "Sharia",
                    "lastName": "Zammett",
                    "homeOfficeId": "CHI",
                    "status": "Regular-Terminated",
                    "globalTitle": "Reception",
                    "jobFunction": "Operations",
                    "title": "Anonymized Business Title"
                },
                {
                    "id": "12733",
                    "name": "Sharia Cuttle",
                    "hostOfficeId": "SIN",
                    "firstName": "Sharia",
                    "lastName": "Cuttle",
                    "homeOfficeId": "SIN",
                    "status": "Regular-Terminated",
                    "globalTitle": "Managing Director and Partner",
                    "jobFunction": "MD and Partner",
                    "title": "Anonymized Business Title"
                },
                {
                    "id": "171377",
                    "name": "Sharia Nickell",
                    "hostOfficeId": "DAL",
                    "firstName": "Sharia",
                    "lastName": "Nickell",
                    "homeOfficeId": "DAL",
                    "status": "Regular-Terminated",
                    "globalTitle": "Associate",
                    "jobFunction": "Associate",
                    "title": "Associate"
                },
                {
                    "id": "255217",
                    "name": "Sharia Allison",
                    "hostOfficeId": "TOK",
                    "firstName": "Sharia",
                    "lastName": "Allison",
                    "homeOfficeId": "TOK",
                    "status": "Regular-Terminated",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                },
                {
                    "id": "266162",
                    "name": "Sharia Troutbeck",
                    "hostOfficeId": "MEX",
                    "firstName": "Sharia",
                    "lastName": "Troutbeck",
                    "homeOfficeId": "MEX",
                    "status": "Regular-Terminated",
                    "globalTitle": "Consultant",
                    "jobFunction": "Consultant",
                    "title": "Consultant"
                }
            ],
            "totalCount": 12
        }
    }
}
```
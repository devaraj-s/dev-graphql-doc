## Use case 1: User wishes to find a person in the employee list  

**Test case 1: Find By First Name**  

<summary>Request</summary>
<pre><code>
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
</code></pre>  

<summary>Response</summary>
<pre><code>
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
</code></pre>  

**Test case 2: Find By Job Function Name**  

<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  

## Use case 2: User wishes to search for a person in employee list by providing certain filter values  

**Test case 1: Multiple search filters used with find and filter Type:OR/NOT**  

<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
  
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
    
**Test case 2: Filter by First name and Last name using filterType : AND**  
  
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
## Use case 3: "DataSet" : User wants to search for specific group of people in employee list and available datasets are BCG_IT , BCG_ALUMINI , BCG_REGULAR , BCG_VENDORS , BCG_ALL  
  
**Test case 1: Search query to filter on First name on dataset BCG_REGULAR**  
  
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
   
**Test case 2: Search by firstname and dataset = BCG_IT**  
  
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
## Use case 4: "Pagination" :User wants to see the number of records to display in viewport.This result set should be mutable.Pagination is achievable through limit and offset parameters in People Search  

**Test case 1: Filter By First name using dataset and limit=10**  
  
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
<details>
<summary>Response</summary>
<pre><code>
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
          }
    }
}
</code></pre>
</details>  
   
## Use case 5:  "Sorting" :User wants to get the response in a sequential order  
  
**Test case 1: Filter by First name and Sort By Last name - default Ascending sort**  
  
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
   
**Test case 2: Sort By First name in ascending order**   
   
<details>
<summary>Request</summary>
<pre><code>
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
</pre></code>
</details>  
   
**Test case 3: Multiple Sort By First name and Last name in ascending order**  

<details>
<summary>Request</summary>
<pre><code>
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
</code><pre>
</details>  
   
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
   
## Use case 6: Fuzzy Search A fuzzy matching program operates like a spell checker and spelling-error corrector.  
   
**Test case 1: First name and Last name both have spelling mistakes**   
  
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
   
## Use case 7: Type-Ahead Search -  People API also supports Auto-complete feature.  Sort By can be used as well on specific fields.  

**Test case 1: Type Ahead Search with Location Filter and DataSet**  
   
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
   
## Use case 8: Search with Single Character  
  
**Test case 1: Filter by Last Name with single char**  
  
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
   
## Use case 9 :Aggregation - resultFilter - Used for Aggregation / Grouping the fields specified in search query.Multiple or single filter can be used in single query.    
  
**Test case 1 : Filter by First Name and Group By job function**  
  
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
  
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
   
**Test case 2: Aggregation along with Nested filter fields**  
   
<details>
<summary>Request</summary>
<pre><code>
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
</code></pre>
</details>  
   
<details>
<summary>Response</summary>
<pre><code>
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
</code></pre>
</details>  
  
## Code
```graphql
query{
  peopleSearch(find:"suresh"){
    totalCount
    employees{
      id
      name
      firstName
    }
  }
}
```
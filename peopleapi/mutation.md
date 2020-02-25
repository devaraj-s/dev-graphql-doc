# PreferncesAPIMutation
Graph based mutation to store an employee's preferences and create teams
**preference** (`input`: [InputPreference](inputpreference)) : [OutputPreference](peopleapi/object#outputpreference)

Add user preferences

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `input` | [InputPreference](inputpreference) |  |

**team** (`input`: [TeamInput](teaminput)) : [TeamOutput](peopleapi/object#teamoutput)

Create Team

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `input` | [TeamInput](teaminput) |  |

**deleteTeam** (`_id`: [String](peopleapi/scalar#string)) : [TeamOutput](peopleapi/object#teamoutput)

Delete Team

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](peopleapi/scalar#string) |  |

**updateTeam** (`_id`: [String](peopleapi/scalar#string), `fieldsToUpdate`: [TeamInput](teaminput)) : [TeamOutput](peopleapi/object#teamoutput)

Update Team

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](peopleapi/scalar#string) |  |
| `fieldsToUpdate` | [TeamInput](teaminput) |  |

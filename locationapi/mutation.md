# PreferncesAPIMutation
Graph based mutation to store an employee's preferences and create teams
**preference** (`input`: [InputPreference](inputpreference)) : [OutputPreference](locationapi/object#outputpreference)

Add user preferences

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `input` | [InputPreference](inputpreference) |  |

**team** (`input`: [TeamInput](teaminput)) : [TeamOutput](locationapi/object#teamoutput)

Create Team

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `input` | [TeamInput](teaminput) |  |

**deleteTeam** (`_id`: [String](locationapi/scalar#string)) : [TeamOutput](locationapi/object#teamoutput)

Delete Team

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](locationapi/scalar#string) |  |

**updateTeam** (`_id`: [String](locationapi/scalar#string), `fieldsToUpdate`: [TeamInput](teaminput)) : [TeamOutput](locationapi/object#teamoutput)

Update Team

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](locationapi/scalar#string) |  |
| `fieldsToUpdate` | [TeamInput](teaminput) |  |

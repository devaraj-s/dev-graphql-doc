---
layout: default
---
# Enums
Enums represent possible sets of values for a field.

For example, the `Issue` object has a field called `state`. The state is an enum (specifically, of type `IssueState`) because it may be `OPEN` or `CLOSED`.

## EventVisibility
Visibility of the event

| Value  | Description               | Deprecated      | Reason |
| --------- | ------------------ | ---------------- | ---------- |
| `PRIVATE` |  | No |  |
| `PUBLIC` |  | No |  |

## FilterType
Filter type can be either OR or AND, used with filters argument. Default is OR

| Value  | Description               | Deprecated      | Reason |
| --------- | ------------------ | ---------------- | ---------- |
| `OR` |  | No |  |
| `AND` |  | No |  |
| `NOT` |  | No |  |

## Category
Filter type can be either OR or AND, used with filters argument. Default is OR

| Value  | Description               | Deprecated      | Reason |
| --------- | ------------------ | ---------------- | ---------- |
| `TRAVEL` |  | No |  |
| `CONFERENCE` |  | No |  |
| `WORKSHOP` |  | No |  |
| `VACATION` |  | No |  |
| `MEETING` |  | No |  |
| `SOCIAL` |  | No |  |
| `COMMUNITY` |  | No |  |

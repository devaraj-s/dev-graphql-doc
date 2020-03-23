# Enums
Enums represent possible sets of values for a field.

For example, the `Issue` object has a field called `state`. The state is an enum (specifically, of type `IssueState`) because it may be `OPEN` or `CLOSED`.

## FilterType
Filter type can be either OR or AND, used with filters argument. Default is OR

| Value  | Description               | Deprecated      | Reason |
| --------- | ------------------ | ---------------- | ---------- |
| `OR` |  | No |  |
| `AND` |  | No |  |
| `NOT` |  | No |  |

## RegionType
Type of the office location

| Value  | Description               | Deprecated      | Reason |
| --------- | ------------------ | ---------------- | ---------- |
| `WESA` |  | No |  |
| `NAMR` |  | No |  |
| `CEMA` |  | No |  |
| `APAC` |  | No |  |
| `CUSTOM` |  | No |  |

## LocationType
Type of the office location

| Value  | Description               | Deprecated      | Reason |
| --------- | ------------------ | ---------------- | ---------- |
| `BCG_OFFICE` |  | No |  |
| `CAMPUS` |  | No |  |
| `VENUE` |  | No |  |

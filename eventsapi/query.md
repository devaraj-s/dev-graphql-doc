# EventsAPIFetch
Graph based API to get events information, including their location.
**event** (`_id`: [String](scalar#string)) : [OutputEvent](object#outputevent)

Fetch event by id

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](scalar#string) | Id of an event to be requested |

**events** (`filter`: [String](scalar#string), `from`: [String](scalar#string), `to`: [String](scalar#string), `filters`: [[String]](scalar#string), `filterType`: [FilterType](enum#filtertype)) : [[OutputEvent]](object#outputevent)

Fetch events by any filter, such as locationId=LON

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `filter` | [String](scalar#string) | Filter events on the basis of input fields, eg. locationId=LON |
| `from` | [String](scalar#string) | Utc Time number number to query events from date. Default is current time of the request sent. |
| `to` | [String](scalar#string) | Utc time stamp number to query events to time. Default is one month after the current time. |
| `filters` | [[String]](scalar#string) | One or more filters separated by commas(,). Use filterType enum with this |
| `filterType` | [FilterType](enum#filtertype) | Filter type OR/AND/NOT. Default is OR |

**eventsFilter** (`from`: [String](scalar#string), `to`: [String](scalar#string), `filters`: [[search]](search)) : [[OutputEvent]](object#outputevent)

Fetch events by any filter, such as locationId=LON

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `from` | [String](scalar#string) | Utc Time number number to query events from date. Default is current time of the request sent. |
| `to` | [String](scalar#string) | Utc time stamp number to query events to time. Default is one month after the current time. |
| `filters` | [[search]](search) | Two or more filters separated by commas(,). Use filterType enum with this |

**categories**  : [[String]](scalar#string)

Fetch all event categories

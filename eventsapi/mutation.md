---
layout: default
---
# EventsAPIMutation
Graph based API to get events information, including their location.
**event** (`input`: [InputEvent](inputevent)) : [OutputEvent](object#outputevent)

Create event

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `input` | [InputEvent](inputevent) | Event type |

**deleteEvent** (`_id`: [String](scalar#string)) : [OutputEvent](object#outputevent)

Delete an event with provided _id

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](scalar#string) | Use the Event Id |

**updateEvent** (`_id`: [String](scalar#string), `fieldsToUpdate`: [InputEvent](inputevent)) : [OutputEvent](object#outputevent)

Update an event for given _id

| Argument  | Type               | Description      |
| --------- | ------------------ | ---------------- |
| `_id` | [String](scalar#string) | Use the Event Id |
| `fieldsToUpdate` | [InputEvent](inputevent) |  |

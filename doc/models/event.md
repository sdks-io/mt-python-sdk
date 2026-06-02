
# Event

## Structure

`Event`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `resource` | `str` | Required | The type of resource for the event. |
| `event_name` | `str` | Required | The name of the event. |
| `event_time` | `datetime` | Required | The time of the event. |
| `data` | `Any` | Required | The body of the event. |
| `entity_id` | `str` | Required | The ID of the entity for the event. |

## Example (as JSON)

```json
{
  "id": "000022e2-0000-0000-0000-000000000000",
  "object": "object2",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "resource": "resource0",
  "event_name": "event_name8",
  "event_time": "2016-03-13T12:52:32.123Z",
  "data": {
    "key1": "val1",
    "key2": "val2"
  },
  "entity_id": "entity_id8"
}
```


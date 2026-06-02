# Event

```python
event_controller = client.event
```

## Class Name

`EventController`

## Methods

* [List Events](../../doc/controllers/event.md#list-events)
* [Get Event](../../doc/controllers/event.md#get-event)


# List Events

```python
def list_events(self,
               after_cursor=None,
               per_page=None,
               event_time_start=None,
               event_time_end=None,
               resource=None,
               entity_id=None,
               event_name=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `event_time_start` | `datetime` | Query, Optional | An inclusive lower bound for when the event occurred |
| `event_time_end` | `datetime` | Query, Optional | An inclusive upper bound for when the event occurred |
| `resource` | `str` | Query, Optional | - |
| `entity_id` | `str` | Query, Optional | - |
| `event_name` | `str` | Query, Optional | - |

## Response Type

**200**: successful

[`List[Event]`](../../doc/models/event.md)

## Example Usage

```python
result = event_controller.list_events()
print(result)
```


# Get Event

```python
def get_event(self,
             id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | event id |

## Response Type

**200**: successful

[`Event`](../../doc/models/event.md)

## Example Usage

```python
id = 'id0'

result = event_controller.get_event(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


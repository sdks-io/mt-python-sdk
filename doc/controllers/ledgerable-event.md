# Ledgerable Event

```python
ledgerable_event_api = client.ledgerable_event
```

## Class Name

`LedgerableEventApi`

## Methods

* [Create Ledgerable Event](../../doc/controllers/ledgerable-event.md#create-ledgerable-event)
* [Get Ledgerable Event](../../doc/controllers/ledgerable-event.md#get-ledgerable-event)


# Create Ledgerable Event

Translation missing: en.openapi.descriptions.ledger.operations.create_ledgerable_event

```python
def create_ledgerable_event(self,
                           idempotency_key=None,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`LedgerableEventCreateRequest`](../../doc/models/ledgerable-event-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerableEvent`](../../doc/models/ledgerable-event.md).

## Example Usage

```python
body = LedgerableEventCreateRequest(
    name='name6',
    amount=218,
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledgerable_event_api.create_ledgerable_event(
    body=body
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Ledgerable Event

Get details on a single ledgerable event.

```python
def get_ledgerable_event(self,
                        id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerableEvent`](../../doc/models/ledgerable-event.md).

## Example Usage

```python
id = 'id0'

result = ledgerable_event_api.get_ledgerable_event(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


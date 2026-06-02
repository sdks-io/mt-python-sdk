# Ledger Event Handler

```python
ledger_event_handler_controller = client.ledger_event_handler
```

## Class Name

`LedgerEventHandlerController`

## Methods

* [List Ledger Event Handlers](../../doc/controllers/ledger-event-handler.md#list-ledger-event-handlers)
* [Create Ledger Event Handler](../../doc/controllers/ledger-event-handler.md#create-ledger-event-handler)
* [Get Ledger Event Handler](../../doc/controllers/ledger-event-handler.md#get-ledger-event-handler)
* [Delete Ledger Event Handler](../../doc/controllers/ledger-event-handler.md#delete-ledger-event-handler)


# List Ledger Event Handlers

Get a list of ledger event handlers.

```python
def list_ledger_event_handlers(self,
                              after_cursor=None,
                              per_page=None,
                              metadata=None,
                              name=None,
                              created_at=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `name` | `str` | Query, Optional | - |
| `created_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the posted at timestamp. For example, for all times after Jan 1 2000 12:00 UTC, use created_at%5Bgt%5D=2000-01-01T12:00:00Z. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[LedgerEventHandler]`](../../doc/models/ledger-event-handler.md).

## Example Usage

```python
result = ledger_event_handler_controller.list_ledger_event_handlers()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Ledger Event Handler

```python
def create_ledger_event_handler(self,
                               idempotency_key=None,
                               body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`LedgerEventHandlerCreateRequest`](../../doc/models/ledger-event-handler-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerEventHandler`](../../doc/models/ledger-event-handler.md).

## Example Usage

```python
body = LedgerEventHandlerCreateRequest(
    name='name6',
    ledger_transaction_template=LedgerEventHandlerLedgerTransactionTemplate(
        description='description4',
        effective_at='effective_at2',
        ledger_entries=[
            LedgerEventHandlerLedgerEntries(
                amount='amount6',
                direction='direction0',
                ledger_account_id='ledger_account_id8'
            )
        ],
        metadata={
            'key': 'value',
            'foo': 'bar',
            'modern': 'treasury'
        }
    ),
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_event_handler_controller.create_ledger_event_handler(
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
| 400 | parameter_invalid | `ApiException` |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Ledger Event Handler

Get details on a single ledger event handler.

```python
def get_ledger_event_handler(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerEventHandler`](../../doc/models/ledger-event-handler.md).

## Example Usage

```python
id = 'id0'

result = ledger_event_handler_controller.get_ledger_event_handler(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Delete Ledger Event Handler

Archive a ledger event handler.

```python
def delete_ledger_event_handler(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerEventHandler`](../../doc/models/ledger-event-handler.md).

## Example Usage

```python
id = 'id0'

result = ledger_event_handler_controller.delete_ledger_event_handler(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


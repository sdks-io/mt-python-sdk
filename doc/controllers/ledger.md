# Ledger

```python
ledger_api = client.ledger
```

## Class Name

`LedgerApi`

## Methods

* [List Ledgers](../../doc/controllers/ledger.md#list-ledgers)
* [Create Ledger](../../doc/controllers/ledger.md#create-ledger)
* [Get Ledger](../../doc/controllers/ledger.md#get-ledger)
* [Update Ledger](../../doc/controllers/ledger.md#update-ledger)
* [Delete Ledger](../../doc/controllers/ledger.md#delete-ledger)


# List Ledgers

Get a list of ledgers.

```python
def list_ledgers(self,
                after_cursor=None,
                per_page=None,
                metadata=None,
                updated_at=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `updated_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the posted at timestamp. For example, for all times after Jan 1 2000 12:00 UTC, use updated_at%5Bgt%5D=2000-01-01T12:00:00Z. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[Ledger]`](../../doc/models/ledger.md).

## Example Usage

```python
result = ledger_api.list_ledgers()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Ledger

Create a ledger.

```python
def create_ledger(self,
                 idempotency_key=None,
                 body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`LedgerCreateRequest`](../../doc/models/ledger-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Ledger`](../../doc/models/ledger.md).

## Example Usage

```python
body = LedgerCreateRequest(
    name='name6',
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_api.create_ledger(
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


# Get Ledger

Get details on a single ledger.

```python
def get_ledger(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Ledger`](../../doc/models/ledger.md).

## Example Usage

```python
id = 'id0'

result = ledger_api.get_ledger(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Ledger

Update the details of a ledger.

```python
def update_ledger(self,
                 id,
                 body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `body` | [`LedgerUpdateRequest`](../../doc/models/ledger-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Ledger`](../../doc/models/ledger.md).

## Example Usage

```python
id = 'id0'

body = LedgerUpdateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_api.update_ledger(
    id,
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
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Delete Ledger

Delete a ledger.

```python
def delete_ledger(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Ledger`](../../doc/models/ledger.md).

## Example Usage

```python
id = 'id0'

result = ledger_api.delete_ledger(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


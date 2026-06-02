# Ledger Account Statement

```python
ledger_account_statement_api = client.ledger_account_statement
```

## Class Name

`LedgerAccountStatementApi`

## Methods

* [Create Ledger Account Statement](../../doc/controllers/ledger-account-statement.md#create-ledger-account-statement)
* [Get Ledger Account Statement](../../doc/controllers/ledger-account-statement.md#get-ledger-account-statement)


# Create Ledger Account Statement

Create a ledger account statement.

```python
def create_ledger_account_statement(self,
                                   idempotency_key=None,
                                   body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`LedgerAccountStatementCreateRequest`](../../doc/models/ledger-account-statement-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerAccountStatement`](../../doc/models/ledger-account-statement.md).

## Example Usage

```python
body = LedgerAccountStatementCreateRequest(
    ledger_account_id='000012de-0000-0000-0000-000000000000',
    effective_at_lower_bound=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
    effective_at_upper_bound=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_account_statement_api.create_ledger_account_statement(
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


# Get Ledger Account Statement

Get details on a single ledger account statement.

```python
def get_ledger_account_statement(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerAccountStatement`](../../doc/models/ledger-account-statement.md).

## Example Usage

```python
id = 'id0'

result = ledger_account_statement_api.get_ledger_account_statement(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Ledger Account

```python
ledger_account_controller = client.ledger_account
```

## Class Name

`LedgerAccountController`

## Methods

* [List Ledger Accounts](../../doc/controllers/ledger-account.md#list-ledger-accounts)
* [Create Ledger Account](../../doc/controllers/ledger-account.md#create-ledger-account)
* [Get Ledger Account](../../doc/controllers/ledger-account.md#get-ledger-account)
* [Update Ledger Account](../../doc/controllers/ledger-account.md#update-ledger-account)
* [Delete Ledger Account](../../doc/controllers/ledger-account.md#delete-ledger-account)


# List Ledger Accounts

Get a list of ledger accounts.

```python
def list_ledger_accounts(self,
                        after_cursor=None,
                        per_page=None,
                        metadata=None,
                        id=None,
                        name=None,
                        ledger_id=None,
                        currency=None,
                        balances=None,
                        created_at=None,
                        updated_at=None,
                        ledger_account_category_id=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `id` | `str` | Query, Optional | - |
| `name` | `str` | Query, Optional | - |
| `ledger_id` | `str` | Query, Optional | - |
| `currency` | `str` | Query, Optional | - |
| `balances` | [`Balances2`](../../doc/models/balances-2.md) | Query, Optional | Use `balances[effective_at_lower_bound]` and `balances[effective_at_upper_bound]` to get the balances change between the two timestamps. The lower bound is inclusive while the upper bound is exclusive of the provided timestamps. If no value is supplied the balances will be retrieved not including that bound. |
| `created_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the created at timestamp. For example, for all times after Jan 1 2000 12:00 UTC, use created_at%5Bgt%5D=2000-01-01T12:00:00Z. |
| `updated_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the updated at timestamp. For example, for all times after Jan 1 2000 12:00 UTC, use updated_at%5Bgt%5D=2000-01-01T12:00:00Z. |
| `ledger_account_category_id` | `str` | Query, Optional | - |

## Response Type

**200**: successful

[`List[LedgerAccount]`](../../doc/models/ledger-account.md)

## Example Usage

```python
result = ledger_account_controller.list_ledger_accounts()
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create Ledger Account

Create a ledger account.

```python
def create_ledger_account(self,
                         idempotency_key=None,
                         body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`LedgerAccountCreateRequest`](../../doc/models/ledger-account-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

[`LedgerAccount`](../../doc/models/ledger-account.md)

## Example Usage

```python
body = LedgerAccountCreateRequest(
    name='name6',
    normal_balance=NormalBalanceEnum.CREDIT,
    ledger_id='00002576-0000-0000-0000-000000000000',
    currency='currency6',
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_account_controller.create_ledger_account(
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Ledger Account

Get details on a single ledger account.

```python
def get_ledger_account(self,
                      id,
                      balances=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `balances` | [`Balances3`](../../doc/models/balances-3.md) | Query, Optional | Use `balances[effective_at_lower_bound]` and `balances[effective_at_upper_bound]` to get the balances change between the two timestamps. The lower bound is inclusive while the upper bound is exclusive of the provided timestamps. If no value is supplied the balances will be retrieved not including that bound. Use `balances[as_of_lock_version]` to retrieve a balance as of a specific Ledger Account `lock_version`. |

## Response Type

**200**: successful

[`LedgerAccount`](../../doc/models/ledger-account.md)

## Example Usage

```python
id = 'id0'

result = ledger_account_controller.get_ledger_account(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Ledger Account

Update the details of a ledger account.

```python
def update_ledger_account(self,
                         id,
                         body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `body` | [`LedgerAccountUpdateRequest`](../../doc/models/ledger-account-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

[`LedgerAccount`](../../doc/models/ledger-account.md)

## Example Usage

```python
id = 'id0'

body = LedgerAccountUpdateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_account_controller.update_ledger_account(
    id,
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Delete Ledger Account

Delete a ledger account.

```python
def delete_ledger_account(self,
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

[`LedgerAccount`](../../doc/models/ledger-account.md)

## Example Usage

```python
id = 'id0'

result = ledger_account_controller.delete_ledger_account(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


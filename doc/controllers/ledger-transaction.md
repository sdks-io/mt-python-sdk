# Ledger Transaction

```python
ledger_transaction_api = client.ledger_transaction
```

## Class Name

`LedgerTransactionApi`

## Methods

* [Create Ledger Transaction Reversal](../../doc/controllers/ledger-transaction.md#create-ledger-transaction-reversal)
* [List Ledger Transaction Versions](../../doc/controllers/ledger-transaction.md#list-ledger-transaction-versions)
* [List Ledger Transactions](../../doc/controllers/ledger-transaction.md#list-ledger-transactions)
* [Create Ledger Transaction](../../doc/controllers/ledger-transaction.md#create-ledger-transaction)
* [Get Ledger Transaction](../../doc/controllers/ledger-transaction.md#get-ledger-transaction)
* [Update Ledger Transaction](../../doc/controllers/ledger-transaction.md#update-ledger-transaction)
* [List Ledger Transaction Versions 1](../../doc/controllers/ledger-transaction.md#list-ledger-transaction-versions-1)


# Create Ledger Transaction Reversal

Create a ledger transaction reversal.

```python
def create_ledger_transaction_reversal(self,
                                      id,
                                      body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | The id of ledger transaction to reverse. |
| `body` | [`LedgerTransactionReversalCreateRequest`](../../doc/models/ledger-transaction-reversal-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerTransaction`](../../doc/models/ledger-transaction.md).

## Example Usage

```python
id = 'id0'

body = LedgerTransactionReversalCreateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_transaction_api.create_ledger_transaction_reversal(
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
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# List Ledger Transaction Versions

Get a list of ledger transaction versions.

```python
def list_ledger_transaction_versions(self,
                                    after_cursor=None,
                                    per_page=None,
                                    created_at=None,
                                    version=None,
                                    ledger_transaction_id=None,
                                    ledger_account_statement_id=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `created_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the created_at timestamp. For example, for all dates after Jan 1 2000 12:00 UTC, use created_at%5Bgt%5D=2000-01-01T12:00:00Z. |
| `version` | `Dict[str, int]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the version. For example, for all versions after 2, use version%5Bgt%5D=2. |
| `ledger_transaction_id` | `str` | Query, Optional | Get all the ledger transaction versions corresponding to the ID of a ledger transaction. |
| `ledger_account_statement_id` | `str` | Query, Optional | Get all ledger transaction versions that are included in the ledger account statement. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[LedgerTransactionVersion]`](../../doc/models/ledger-transaction-version.md).

## Example Usage

```python
result = ledger_transaction_api.list_ledger_transaction_versions()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# List Ledger Transactions

Get a list of ledger transactions.

```python
def list_ledger_transactions(self,
                            after_cursor=None,
                            per_page=None,
                            id=None,
                            metadata=None,
                            ledger_id=None,
                            ledger_account_id=None,
                            effective_at=None,
                            effective_date=None,
                            posted_at=None,
                            updated_at=None,
                            order_by=None,
                            status=None,
                            external_id=None,
                            ledger_account_category_id=None,
                            ledger_account_payout_id=None,
                            reverses_ledger_transaction_id=None,
                            ledgerable_id=None,
                            ledgerable_type=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `id` | `Dict[str, str]` | Query, Optional | - |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `ledger_id` | `str` | Query, Optional | - |
| `ledger_account_id` | `str` | Query, Optional | - |
| `effective_at` | `Dict[str, datetime]` | Query, Optional | Use "gt" (>), "gte" (>=), "lt" (<), "lte" (<=), or "eq" (=) to filter by effective at. For example, for all transactions after Jan 1 2000, use effective_at%5Bgt%5D=2000-01-01T00:00:00:00.000Z. |
| `effective_date` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by effective date. For example, for all dates after Jan 1 2000, use effective_date%5Bgt%5D=2000-01-01. |
| `posted_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the posted at timestamp. For example, for all times after Jan 1 2000 12:00 UTC, use posted_at%5Bgt%5D=2000-01-01T12:00:00Z. |
| `updated_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the posted at timestamp. For example, for all times after Jan 1 2000 12:00 UTC, use updated_at%5Bgt%5D=2000-01-01T12:00:00Z. |
| `order_by` | [`OrderBy`](../../doc/models/order-by.md) | Query, Optional | Order by `created_at` or `effective_at` in `asc` or `desc` order. For example, to order by `effective_at asc`, use `order_by%5Beffective_at%5D=asc`. Ordering by only one field at a time is supported. |
| `status` | [`Status22`](../../doc/models/status-22.md) | Query, Optional | - |
| `external_id` | `str` | Query, Optional | - |
| `ledger_account_category_id` | `str` | Query, Optional | - |
| `ledger_account_payout_id` | `str` | Query, Optional | - |
| `reverses_ledger_transaction_id` | `str` | Query, Optional | - |
| `ledgerable_id` | `str` | Query, Optional | - |
| `ledgerable_type` | [`LedgerableType6`](../../doc/models/ledgerable-type-6.md) | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[LedgerTransaction]`](../../doc/models/ledger-transaction.md).

## Example Usage

```python
result = ledger_transaction_api.list_ledger_transactions()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | parameter invalid | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create Ledger Transaction

Create a ledger transaction.

```python
def create_ledger_transaction(self,
                             idempotency_key=None,
                             body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`LedgerTransactionCreateRequest`](../../doc/models/ledger-transaction-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerTransaction`](../../doc/models/ledger-transaction.md).

## Example Usage

```python
body = LedgerTransactionCreateRequest(
    ledger_entries=[
        LedgerEntryCreateRequest(
            amount=60,
            direction=Direction5.CREDIT,
            ledger_account_id='00002600-0000-0000-0000-000000000000',
            metadata={
                'key': 'value',
                'foo': 'bar',
                'modern': 'treasury'
            }
        )
    ],
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_transaction_api.create_ledger_transaction(
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
| 429 | too many requests | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Ledger Transaction

Get details on a single ledger transaction.

```python
def get_ledger_transaction(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerTransaction`](../../doc/models/ledger-transaction.md).

## Example Usage

```python
id = 'id0'

result = ledger_transaction_api.get_ledger_transaction(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Ledger Transaction

Update the details of a ledger transaction.

```python
def update_ledger_transaction(self,
                             id,
                             body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `body` | [`LedgerTransactionUpdateRequest`](../../doc/models/ledger-transaction-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerTransaction`](../../doc/models/ledger-transaction.md).

## Example Usage

```python
id = 'id0'

body = LedgerTransactionUpdateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_transaction_api.update_ledger_transaction(
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
| 400 | parameter_invalid | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 429 | too many requests | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# List Ledger Transaction Versions 1

Get a list of ledger transaction versions.

```python
def list_ledger_transaction_versions_1(self,
                                      id,
                                      after_cursor=None,
                                      per_page=None,
                                      created_at=None,
                                      version=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `created_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the created_at timestamp. For example, for all dates after Jan 1 2000 12:00 UTC, use created_at%5Bgt%5D=2000-01-01T12:00:00Z. |
| `version` | `Dict[str, int]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the version. For example, for all versions after 2, use version%5Bgt%5D=2. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[LedgerTransactionVersion]`](../../doc/models/ledger-transaction-version.md).

## Example Usage

```python
id = 'id0'

result = ledger_transaction_api.list_ledger_transaction_versions_1(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


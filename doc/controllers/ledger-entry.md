# Ledger Entry

```python
ledger_entry_api = client.ledger_entry
```

## Class Name

`LedgerEntryApi`

## Methods

* [List Ledger Entries](../../doc/controllers/ledger-entry.md#list-ledger-entries)
* [Get Ledger Entry](../../doc/controllers/ledger-entry.md#get-ledger-entry)


# List Ledger Entries

Get a list of all ledger entries.

```python
def list_ledger_entries(self,
                       after_cursor=None,
                       per_page=None,
                       id=None,
                       ledger_account_id=None,
                       ledger_transaction_id=None,
                       ledger_account_payout_id=None,
                       effective_date=None,
                       effective_at=None,
                       updated_at=None,
                       as_of_lock_version=None,
                       ledger_account_lock_version=None,
                       ledger_account_category_id=None,
                       ledger_account_statement_id=None,
                       show_deleted=None,
                       direction=None,
                       status=None,
                       order_by=None,
                       show_balances=None,
                       metadata=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `id` | `Dict[str, str]` | Query, Optional | - |
| `ledger_account_id` | `str` | Query, Optional | - |
| `ledger_transaction_id` | `str` | Query, Optional | - |
| `ledger_account_payout_id` | `str` | Query, Optional | - |
| `effective_date` | `Dict[str, date]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the transaction's effective date. Format YYYY-MM-DD |
| `effective_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the transaction's effective time. Format ISO8601 |
| `updated_at` | `Dict[str, datetime]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the posted at timestamp. For example, for all times after Jan 1 2000 12:00 UTC, use updated_at%5Bgt%5D=2000-01-01T12:00:00Z. |
| `as_of_lock_version` | `int` | Query, Optional | Shows all ledger entries that were present on a ledger account at a particular `lock_version`. You must also specify `ledger_account_id`. |
| `ledger_account_lock_version` | `Dict[str, int]` | Query, Optional | Use `gt` (>), `gte` (>=), `lt` (<), `lte` (<=), or `eq` (=) to filter by the lock_version of a ledger account. For example, for all entries created at or before before lock_version 1000 of a ledger account, use `ledger_account_lock_version%5Blte%5D=1000`. |
| `ledger_account_category_id` | `str` | Query, Optional | Get all ledger entries that match the direction specified. One of `credit`, `debit`. |
| `ledger_account_statement_id` | `str` | Query, Optional | Get all ledger entries that are included in the ledger account statement. |
| `show_deleted` | `bool` | Query, Optional | If true, response will include ledger entries that were deleted. When you update a ledger transaction to specify a new set of entries, the previous entries are deleted. |
| `direction` | [`Direction15`](../../doc/models/direction-15.md) | Query, Optional | If true, response will include ledger entries that were deleted. When you update a ledger transaction to specify a new set of entries, the previous entries are deleted. |
| `status` | [`Status22`](../../doc/models/status-22.md) | Query, Optional | Get all ledger entries that match the status specified. One of `pending`, `posted`, or `archived`. |
| `order_by` | [`OrderBy`](../../doc/models/order-by.md) | Query, Optional | Order by `created_at` or `effective_at` in `asc` or `desc` order. For example, to order by `effective_at asc`, use `order_by%5Beffective_at%5D=asc`. Ordering by only one field at a time is supported. |
| `show_balances` | `bool` | Query, Optional | If true, response will include the balances attached to the ledger entry. If there is no balance available, null will be returned instead. |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[LedgerEntry]`](../../doc/models/ledger-entry.md).

## Example Usage

```python
result = ledger_entry_api.list_ledger_entries()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Ledger Entry

Get details on a single ledger entry.

```python
def get_ledger_entry(self,
                    id,
                    show_balances=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `show_balances` | `bool` | Query, Optional | If true, response will include the balances attached to the ledger entry. If there is no balance available, null will be returned instead. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerEntry`](../../doc/models/ledger-entry.md).

## Example Usage

```python
id = 'id0'

result = ledger_entry_api.get_ledger_entry(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


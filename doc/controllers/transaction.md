# Transaction

```python
transaction_api = client.transaction
```

## Class Name

`TransactionApi`

## Methods

* [List Transactions](../../doc/controllers/transaction.md#list-transactions)
* [Get Transaction](../../doc/controllers/transaction.md#get-transaction)
* [Update Transaction](../../doc/controllers/transaction.md#update-transaction)


# List Transactions

Get a list of all transactions.

```python
def list_transactions(self,
                     after_cursor=None,
                     per_page=None,
                     internal_account_id=None,
                     virtual_account_id=None,
                     posted=None,
                     as_of_date_start=None,
                     as_of_date_end=None,
                     direction=None,
                     counterparty_id=None,
                     payment_type=None,
                     transactable_type=None,
                     description=None,
                     vendor_id=None,
                     metadata=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `internal_account_id` | `uuid\|str` | Query, Optional | Specify `internal_account_id` if you wish to see transactions to/from a specific account. |
| `virtual_account_id` | `uuid\|str` | Query, Optional | - |
| `posted` | `bool` | Query, Optional | Either `true` or `false`. |
| `as_of_date_start` | `date` | Query, Optional | Filters transactions with an `as_of_date` starting on or after the specified date (YYYY-MM-DD). |
| `as_of_date_end` | `date` | Query, Optional | Filters transactions with an `as_of_date` starting on or before the specified date (YYYY-MM-DD). |
| `direction` | `str` | Query, Optional | - |
| `counterparty_id` | `uuid\|str` | Query, Optional | - |
| `payment_type` | `str` | Query, Optional | - |
| `transactable_type` | `str` | Query, Optional | - |
| `description` | `str` | Query, Optional | Filters for transactions including the queried string in the description. |
| `vendor_id` | `str` | Query, Optional | Filters for transactions including the queried vendor id (an identifier given to transactions by the bank). |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[Transaction]`](../../doc/models/transaction.md).

## Example Usage

```python
result = transaction_api.list_transactions()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Get Transaction

Get details on a single transaction.

```python
def get_transaction(self,
                   id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | Transaction ID |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Transaction`](../../doc/models/transaction.md).

## Example Usage

```python
id = 'id0'

result = transaction_api.get_transaction(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Transaction

Update a single transaction.

```python
def update_transaction(self,
                      id,
                      body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | Transaction ID |
| `body` | [`IncomingPaymentDetailUpdateRequest`](../../doc/models/incoming-payment-detail-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Transaction`](../../doc/models/transaction.md).

## Example Usage

```python
id = 'id0'

result = transaction_api.update_transaction(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


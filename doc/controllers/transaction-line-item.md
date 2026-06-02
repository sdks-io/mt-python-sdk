# Transaction Line Item

```python
transaction_line_item_api = client.transaction_line_item
```

## Class Name

`TransactionLineItemApi`


# List Transaction Line Items

```python
def list_transaction_line_items(self,
                               transaction_id,
                               after_cursor=None,
                               mtype=None,
                               per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transaction_id` | `str` | Template, Required | transaction_id |
| `after_cursor` | `str` | Query, Optional | - |
| `mtype` | [`Type16`](../../doc/models/type-16.md) | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[TransactionLineItem]`](../../doc/models/transaction-line-item.md).

## Example Usage

```python
transaction_id = 'transaction_id8'

result = transaction_line_item_api.list_transaction_line_items(transaction_id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


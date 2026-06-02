# Transaction Line Item

```python
transaction_line_item_controller = client.transaction_line_item
```

## Class Name

`TransactionLineItemController`


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
| `mtype` | [`Type16Enum`](../../doc/models/type-16-enum.md) | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

[`List[TransactionLineItem]`](../../doc/models/transaction-line-item.md)

## Example Usage

```python
transaction_id = 'transaction_id8'

result = transaction_line_item_controller.list_transaction_line_items(transaction_id)
print(result)
```


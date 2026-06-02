# Line Item

```python
line_item_controller = client.line_item
```

## Class Name

`LineItemController`

## Methods

* [List Line Items](../../doc/controllers/line-item.md#list-line-items)
* [Get Line Item](../../doc/controllers/line-item.md#get-line-item)
* [Update Line Item](../../doc/controllers/line-item.md#update-line-item)


# List Line Items

Get a list of line items

```python
def list_line_items(self,
                   itemizable_id,
                   itemizable_type,
                   after_cursor=None,
                   per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `itemizable_id` | `str` | Template, Required | The ID of the payment order or expected payment. |
| `itemizable_type` | [`ItemizableType1Enum`](../../doc/models/itemizable-type-1-enum.md) | Template, Required | One of `payment_orders` or `expected_payments`. |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

[`List[LineItem]`](../../doc/models/line-item.md)

## Example Usage

```python
itemizable_id = 'itemizable_id4'

itemizable_type = ItemizableType1Enum.EXPECTED_PAYMENTS

result = line_item_controller.list_line_items(
    itemizable_id,
    itemizable_type
)
print(result)
```


# Get Line Item

Get a single line item

```python
def get_line_item(self,
                 itemizable_id,
                 itemizable_type,
                 id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `itemizable_id` | `str` | Template, Required | The ID of the payment order or expected payment. |
| `itemizable_type` | [`ItemizableType1Enum`](../../doc/models/itemizable-type-1-enum.md) | Template, Required | One of `payment_orders` or `expected_payments`. |
| `id` | `str` | Template, Required | The ID of the line item. |

## Response Type

**200**: successful

[`LineItem`](../../doc/models/line-item.md)

## Example Usage

```python
itemizable_id = 'itemizable_id4'

itemizable_type = ItemizableType1Enum.EXPECTED_PAYMENTS

id = 'id0'

result = line_item_controller.get_line_item(
    itemizable_id,
    itemizable_type,
    id
)
print(result)
```


# Update Line Item

```python
def update_line_item(self,
                    itemizable_id,
                    itemizable_type,
                    id,
                    body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `itemizable_id` | `str` | Template, Required | The ID of the payment order or expected payment. |
| `itemizable_type` | [`ItemizableType1Enum`](../../doc/models/itemizable-type-1-enum.md) | Template, Required | One of `payment_orders` or `expected_payments`. |
| `id` | `str` | Template, Required | The ID of the line item. |
| `body` | [`LineItemUpdateRequest`](../../doc/models/line-item-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

[`LineItem`](../../doc/models/line-item.md)

## Example Usage

```python
itemizable_id = 'itemizable_id4'

itemizable_type = ItemizableType1Enum.EXPECTED_PAYMENTS

id = 'id0'

body = LineItemUpdateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = line_item_controller.update_line_item(
    itemizable_id,
    itemizable_type,
    id,
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


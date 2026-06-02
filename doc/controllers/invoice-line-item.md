# Invoice Line Item

```python
invoice_line_item_controller = client.invoice_line_item
```

## Class Name

`InvoiceLineItemController`

## Methods

* [List Invoice Line Items](../../doc/controllers/invoice-line-item.md#list-invoice-line-items)
* [Create Invoice Line Item](../../doc/controllers/invoice-line-item.md#create-invoice-line-item)
* [Get Invoice Line Item](../../doc/controllers/invoice-line-item.md#get-invoice-line-item)
* [Update Invoice Line Item](../../doc/controllers/invoice-line-item.md#update-invoice-line-item)
* [Delete Invoice Line Item](../../doc/controllers/invoice-line-item.md#delete-invoice-line-item)


# List Invoice Line Items

```python
def list_invoice_line_items(self,
                           invoice_id,
                           after_cursor=None,
                           per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoice_id` | `str` | Template, Required | invoice_id |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[InvoiceLineItem]`](../../doc/models/invoice-line-item.md).

## Example Usage

```python
invoice_id = 'invoice_id0'

result = invoice_line_item_controller.list_invoice_line_items(invoice_id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Invoice Line Item

```python
def create_invoice_line_item(self,
                            invoice_id,
                            idempotency_key=None,
                            body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoice_id` | `str` | Template, Required | invoice_id |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`InvoiceLineItemCreateRequest`](../../doc/models/invoice-line-item-create-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`InvoiceLineItem`](../../doc/models/invoice-line-item.md).

## Example Usage

```python
invoice_id = 'invoice_id0'

result = invoice_line_item_controller.create_invoice_line_item(invoice_id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Get Invoice Line Item

```python
def get_invoice_line_item(self,
                         invoice_id,
                         id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoice_id` | `str` | Template, Required | invoice_id |
| `id` | `str` | Template, Required | id |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`InvoiceLineItem`](../../doc/models/invoice-line-item.md).

## Example Usage

```python
invoice_id = 'invoice_id0'

id = 'id0'

result = invoice_line_item_controller.get_invoice_line_item(
    invoice_id,
    id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Invoice Line Item

```python
def update_invoice_line_item(self,
                            invoice_id,
                            id,
                            body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoice_id` | `str` | Template, Required | invoice_id |
| `id` | `str` | Template, Required | id |
| `body` | [`InvoiceLineItemUpdateRequest`](../../doc/models/invoice-line-item-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`InvoiceLineItem`](../../doc/models/invoice-line-item.md).

## Example Usage

```python
invoice_id = 'invoice_id0'

id = 'id0'

result = invoice_line_item_controller.update_invoice_line_item(
    invoice_id,
    id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Invoice Line Item

```python
def delete_invoice_line_item(self,
                            invoice_id,
                            id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `invoice_id` | `str` | Template, Required | invoice_id |
| `id` | `str` | Template, Required | id |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`InvoiceLineItem`](../../doc/models/invoice-line-item.md).

## Example Usage

```python
invoice_id = 'invoice_id0'

id = 'id0'

result = invoice_line_item_controller.delete_invoice_line_item(
    invoice_id,
    id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Invoice

```python
invoice_controller = client.invoice
```

## Class Name

`InvoiceController`

## Methods

* [List Invoices](../../doc/controllers/invoice.md#list-invoices)
* [Create Invoice](../../doc/controllers/invoice.md#create-invoice)
* [Get Invoice](../../doc/controllers/invoice.md#get-invoice)
* [Update Invoice](../../doc/controllers/invoice.md#update-invoice)


# List Invoices

```python
def list_invoices(self,
                 after_cursor=None,
                 per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[Invoice]`](../../doc/models/invoice.md).

## Example Usage

```python
result = invoice_controller.list_invoices()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Invoice

```python
def create_invoice(self,
                  idempotency_key=None,
                  body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`InvoiceCreateRequest`](../../doc/models/invoice-create-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Invoice`](../../doc/models/invoice.md).

## Example Usage

```python
result = invoice_controller.create_invoice()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Get Invoice

```python
def get_invoice(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Invoice`](../../doc/models/invoice.md).

## Example Usage

```python
id = 'id0'

result = invoice_controller.get_invoice(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Invoice

```python
def update_invoice(self,
                  id,
                  body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `body` | [`InvoiceUpdateRequest`](../../doc/models/invoice-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Invoice`](../../doc/models/invoice.md).

## Example Usage

```python
id = 'id0'

result = invoice_controller.update_invoice(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


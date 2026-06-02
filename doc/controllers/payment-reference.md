# Payment Reference

```python
payment_reference_api = client.payment_reference
```

## Class Name

`PaymentReferenceApi`

## Methods

* [List Payment References](../../doc/controllers/payment-reference.md#list-payment-references)
* [Get Payment Reference](../../doc/controllers/payment-reference.md#get-payment-reference)


# List Payment References

```python
def list_payment_references(self,
                           after_cursor=None,
                           per_page=None,
                           referenceable_id=None,
                           referenceable_type=None,
                           reference_number=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `referenceable_id` | `str` | Query, Optional | The id of the referenceable to search for. Must be accompanied by the referenceable_type or will return an error. |
| `referenceable_type` | [`ReferenceableType1`](../../doc/models/referenceable-type-1.md) | Query, Optional | One of the referenceable types. This must be accompanied by the id of the referenceable or will return an error. |
| `reference_number` | `str` | Query, Optional | The actual reference number assigned by the bank. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[PaymentReferenceObject]`](../../doc/models/payment-reference-object.md).

## Example Usage

```python
result = payment_reference_api.list_payment_references()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Get Payment Reference

```python
def get_payment_reference(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PaymentReferenceObject`](../../doc/models/payment-reference-object.md).

## Example Usage

```python
id = 'id0'

result = payment_reference_api.get_payment_reference(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


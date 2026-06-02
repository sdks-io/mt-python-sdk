# Payment Reference

```python
payment_reference_controller = client.payment_reference
```

## Class Name

`PaymentReferenceController`

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
| `referenceable_type` | [`ReferenceableType1Enum`](../../doc/models/referenceable-type-1-enum.md) | Query, Optional | One of the referenceable types. This must be accompanied by the id of the referenceable or will return an error. |
| `reference_number` | `str` | Query, Optional | The actual reference number assigned by the bank. |

## Response Type

**200**: successful

[`List[PaymentReferenceObject]`](../../doc/models/payment-reference-object.md)

## Example Usage

```python
result = payment_reference_controller.list_payment_references()
print(result)
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

[`PaymentReferenceObject`](../../doc/models/payment-reference-object.md)

## Example Usage

```python
id = 'id0'

result = payment_reference_controller.get_payment_reference(id)
print(result)
```


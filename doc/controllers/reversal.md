# Reversal

```python
reversal_controller = client.reversal
```

## Class Name

`ReversalController`

## Methods

* [List Reversals](../../doc/controllers/reversal.md#list-reversals)
* [Create Reversal](../../doc/controllers/reversal.md#create-reversal)
* [Get Reversal](../../doc/controllers/reversal.md#get-reversal)


# List Reversals

Get a list of all reversals of a payment order.

```python
def list_reversals(self,
                  payment_order_id,
                  after_cursor=None,
                  per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payment_order_id` | `str` | Template, Required | The ID of the relevant Payment Order. |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

[`List[Reversal]`](../../doc/models/reversal.md)

## Example Usage

```python
payment_order_id = 'payment_order_id6'

result = reversal_controller.list_reversals(payment_order_id)
print(result)
```


# Create Reversal

Create a reversal for a payment order.

```python
def create_reversal(self,
                   payment_order_id,
                   idempotency_key=None,
                   body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payment_order_id` | `uuid\|str` | Template, Required | The ID of the relevant Payment Order. |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`ReversalCreateRequest`](../../doc/models/reversal-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

[`Reversal`](../../doc/models/reversal.md)

## Example Usage

```python
payment_order_id = '0000176c-0000-0000-0000-000000000000'

body = ReversalCreateRequest(
    reason=Reason1Enum.DATE_EARLIER_THAN_INTENDED,
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = reversal_controller.create_reversal(
    payment_order_id,
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Reversal

Get details on a single reversal of a payment order.

```python
def get_reversal(self,
                payment_order_id,
                reversal_id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `payment_order_id` | `uuid\|str` | Template, Required | The id of the payment order being reversed. |
| `reversal_id` | `uuid\|str` | Template, Required | The ID of the reversal. |

## Response Type

**200**: successful

[`Reversal`](../../doc/models/reversal.md)

## Example Usage

```python
payment_order_id = '0000176c-0000-0000-0000-000000000000'

reversal_id = '00000f9e-0000-0000-0000-000000000000'

result = reversal_controller.get_reversal(
    payment_order_id,
    reversal_id
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


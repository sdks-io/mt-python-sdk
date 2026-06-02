# Return

```python
mreturn_controller = client.mreturn
```

## Class Name

`ReturnController`

## Methods

* [List Returns](../../doc/controllers/return.md#list-returns)
* [Create Return](../../doc/controllers/return.md#create-return)
* [Get Return](../../doc/controllers/return.md#get-return)


# List Returns

Get a list of returns.

```python
def list_returns(self,
                after_cursor=None,
                per_page=None,
                internal_account_id=None,
                counterparty_id=None,
                returnable_id=None,
                returnable_type=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `internal_account_id` | `str` | Query, Optional | Specify `internal_account_id` if you wish to see returns to/from a specific account. |
| `counterparty_id` | `str` | Query, Optional | Specify `counterparty_id` if you wish to see returns that occurred with a specific counterparty. |
| `returnable_id` | `str` | Query, Optional | The ID of a valid returnable. Must be accompanied by `returnable_type`. |
| `returnable_type` | [`ReturnableType1Enum`](../../doc/models/returnable-type-1-enum.md) | Query, Optional | One of `payment_order`, `paper_item`, `reversal`, or `incoming_payment_detail`. Must be accompanied by `returnable_id`. |

## Response Type

**200**: successful

[`List[Return]`](../../doc/models/return.md)

## Example Usage

```python
result = mreturn_controller.list_returns()
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create Return

Create a return.

```python
def create_return(self,
                 idempotency_key=None,
                 body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`ReturnCreateRequest`](../../doc/models/return-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

[`Return`](../../doc/models/return.md)

## Example Usage

```python
body = ReturnCreateRequest(
    returnable_id='00000350-0000-0000-0000-000000000000'
)

result = mreturn_controller.create_return(
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Return

Get a single return.

```python
def get_return(self,
              id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | The ID of an existing return. |

## Response Type

**200**: successful

[`Return`](../../doc/models/return.md)

## Example Usage

```python
id = 'id0'

result = mreturn_controller.get_return(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Payment Flow

```python
payment_flow_controller = client.payment_flow
```

## Class Name

`PaymentFlowController`

## Methods

* [List Payment Flows](../../doc/controllers/payment-flow.md#list-payment-flows)
* [Create Payment Flow](../../doc/controllers/payment-flow.md#create-payment-flow)
* [Get Payment Flow](../../doc/controllers/payment-flow.md#get-payment-flow)
* [Update Payment Flow](../../doc/controllers/payment-flow.md#update-payment-flow)


# List Payment Flows

```python
def list_payment_flows(self,
                      after_cursor=None,
                      per_page=None,
                      client_token=None,
                      status=None,
                      counterparty_id=None,
                      receiving_account_id=None,
                      originating_account_id=None,
                      payment_order_id=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `client_token` | `str` | Query, Optional | - |
| `status` | `str` | Query, Optional | - |
| `counterparty_id` | `str` | Query, Optional | - |
| `receiving_account_id` | `str` | Query, Optional | - |
| `originating_account_id` | `str` | Query, Optional | - |
| `payment_order_id` | `str` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[PaymentFlow]`](../../doc/models/payment-flow.md).

## Example Usage

```python
result = payment_flow_controller.list_payment_flows()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Payment Flow

```python
def create_payment_flow(self,
                       idempotency_key=None,
                       body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`PaymentFlowCreateRequest`](../../doc/models/payment-flow-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PaymentFlow`](../../doc/models/payment-flow.md).

## Example Usage

```python
result = payment_flow_controller.create_payment_flow()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Payment Flow

```python
def get_payment_flow(self,
                    id,
                    idempotency_key=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PaymentFlow`](../../doc/models/payment-flow.md).

## Example Usage

```python
id = 'id0'

result = payment_flow_controller.get_payment_flow(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Update Payment Flow

```python
def update_payment_flow(self,
                       id,
                       idempotency_key=None,
                       body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`PaymentFlowUpdateRequest`](../../doc/models/payment-flow-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PaymentFlow`](../../doc/models/payment-flow.md).

## Example Usage

```python
id = 'id0'

body = PaymentFlowUpdateRequest()

result = payment_flow_controller.update_payment_flow(
    id,
    body=body
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


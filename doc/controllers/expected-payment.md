# Expected Payment

```python
expected_payment_api = client.expected_payment
```

## Class Name

`ExpectedPaymentApi`

## Methods

* [List Expected Payments](../../doc/controllers/expected-payment.md#list-expected-payments)
* [Create Expected Payment](../../doc/controllers/expected-payment.md#create-expected-payment)
* [Get Expected Payment](../../doc/controllers/expected-payment.md#get-expected-payment)
* [Update Expected Payment](../../doc/controllers/expected-payment.md#update-expected-payment)
* [Delete Expected Payment](../../doc/controllers/expected-payment.md#delete-expected-payment)


# List Expected Payments

```python
def list_expected_payments(self,
                          after_cursor=None,
                          per_page=None,
                          status=None,
                          internal_account_id=None,
                          direction=None,
                          mtype=None,
                          counterparty_id=None,
                          metadata=None,
                          created_at_lower_bound=None,
                          created_at_upper_bound=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `status` | [`Status20`](../../doc/models/status-20.md) | Query, Optional | One of unreconciled, reconciled, or archived. |
| `internal_account_id` | `str` | Query, Optional | Specify internal_account_id to see expected_payments for a specific account. |
| `direction` | [`Direction15`](../../doc/models/direction-15.md) | Query, Optional | One of credit, debit |
| `mtype` | [`Type13`](../../doc/models/type-13.md) | Query, Optional | One of: ach, au_becs, bacs, book, check, eft, interac, provxchange, rtp,sen, sepa, signet, wire |
| `counterparty_id` | `str` | Query, Optional | Specify counterparty_id to see expected_payments for a specific account. |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `created_at_lower_bound` | `datetime` | Query, Optional | Used to return expected payments created after some datetime |
| `created_at_upper_bound` | `datetime` | Query, Optional | Used to return expected payments created before some datetime |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[ExpectedPayment]`](../../doc/models/expected-payment.md).

## Example Usage

```python
result = expected_payment_api.list_expected_payments()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create Expected Payment

```python
def create_expected_payment(self,
                           idempotency_key=None,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`ExpectedPaymentCreateRequest`](../../doc/models/expected-payment-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ExpectedPayment`](../../doc/models/expected-payment.md).

## Example Usage

```python
body = ExpectedPaymentCreateRequest(
    amount_upper_bound=80,
    amount_lower_bound=142,
    direction=Direction1.CREDIT,
    internal_account_id='0000118a-0000-0000-0000-000000000000',
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = expected_payment_api.create_expected_payment(
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
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Expected Payment

```python
def get_expected_payment(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ExpectedPayment`](../../doc/models/expected-payment.md).

## Example Usage

```python
id = 'id0'

result = expected_payment_api.get_expected_payment(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Expected Payment

```python
def update_expected_payment(self,
                           id,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `body` | [`ExpectedPaymentUpdateRequest`](../../doc/models/expected-payment-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ExpectedPayment`](../../doc/models/expected-payment.md).

## Example Usage

```python
id = 'id0'

body = ExpectedPaymentUpdateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = expected_payment_api.update_expected_payment(
    id,
    body=body
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Delete Expected Payment

```python
def delete_expected_payment(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ExpectedPayment`](../../doc/models/expected-payment.md).

## Example Usage

```python
id = 'id0'

result = expected_payment_api.delete_expected_payment(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | parameter_invalid | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


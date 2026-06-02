# Incoming Payment Detail

```python
incoming_payment_detail_controller = client.incoming_payment_detail
```

## Class Name

`IncomingPaymentDetailController`

## Methods

* [List Incoming Payment Details](../../doc/controllers/incoming-payment-detail.md#list-incoming-payment-details)
* [Get Incoming Payment Detail](../../doc/controllers/incoming-payment-detail.md#get-incoming-payment-detail)
* [Update Incoming Payment Detail](../../doc/controllers/incoming-payment-detail.md#update-incoming-payment-detail)
* [Create Async Incoming Payment Detail](../../doc/controllers/incoming-payment-detail.md#create-async-incoming-payment-detail)


# List Incoming Payment Details

Get a list of Incoming Payment Details.

```python
def list_incoming_payment_details(self,
                                 after_cursor=None,
                                 per_page=None,
                                 direction=None,
                                 status=None,
                                 mtype=None,
                                 as_of_date_start=None,
                                 as_of_date_end=None,
                                 metadata=None,
                                 virtual_account_id=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `direction` | [`Direction15`](../../doc/models/direction-15.md) | Query, Optional | One of `credit` or `debit`. |
| `status` | [`Status21`](../../doc/models/status-21.md) | Query, Optional | The current status of the incoming payment order. One of `pending`, `completed`, or `returned`. |
| `mtype` | [`Type14`](../../doc/models/type-14.md) | Query, Optional | One of: `ach`, `book`, `check`, `eft`, `interac`, `rtp`, `sepa`, `signet`, or `wire`. |
| `as_of_date_start` | `date` | Query, Optional | Filters incoming payment details with an as_of_date starting on or after the specified date (YYYY-MM-DD). |
| `as_of_date_end` | `date` | Query, Optional | Filters incoming payment details with an as_of_date starting on or before the specified date (YYYY-MM-DD). |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `virtual_account_id` | `str` | Query, Optional | If the incoming payment detail is in a virtual account, the ID of the Virtual Account. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[IncomingPaymentDetail]`](../../doc/models/incoming-payment-detail.md).

## Example Usage

```python
result = incoming_payment_detail_controller.list_incoming_payment_details()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Incoming Payment Detail

Get an existing Incoming Payment Detail.

```python
def get_incoming_payment_detail(self,
                               id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | The unique identifier of the incoming payment detail. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`IncomingPaymentDetail`](../../doc/models/incoming-payment-detail.md).

## Example Usage

```python
id = 'id0'

result = incoming_payment_detail_controller.get_incoming_payment_detail(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Incoming Payment Detail

Update an existing Incoming Payment Detail.

```python
def update_incoming_payment_detail(self,
                                  id,
                                  body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | The unique identifier of the incoming payment detail. |
| `body` | [`IncomingPaymentDetailUpdateRequest`](../../doc/models/incoming-payment-detail-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`IncomingPaymentDetail`](../../doc/models/incoming-payment-detail.md).

## Example Usage

```python
id = 'id0'

result = incoming_payment_detail_controller.update_incoming_payment_detail(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create Async Incoming Payment Detail

Simulate Incoming Payment Detail

```python
def create_async_incoming_payment_detail(self,
                                        idempotency_key=None,
                                        body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`IncomingPaymentDetailCreateRequest`](../../doc/models/incoming-payment-detail-create-request.md) | Body, Optional | - |

## Response Type

**202**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AsyncResponse`](../../doc/models/async-response.md).

## Example Usage

```python
result = incoming_payment_detail_controller.create_async_incoming_payment_detail()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 405 | not allowed | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


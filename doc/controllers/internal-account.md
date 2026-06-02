# Internal Account

```python
internal_account_controller = client.internal_account
```

## Class Name

`InternalAccountController`

## Methods

* [List Internal Accounts](../../doc/controllers/internal-account.md#list-internal-accounts)
* [Create Internal Account](../../doc/controllers/internal-account.md#create-internal-account)
* [Get Internal Account](../../doc/controllers/internal-account.md#get-internal-account)
* [Update Internal Account](../../doc/controllers/internal-account.md#update-internal-account)


# List Internal Accounts

```python
def list_internal_accounts(self,
                          after_cursor=None,
                          per_page=None,
                          currency=None,
                          counterparty_id=None,
                          payment_type=None,
                          payment_direction=None,
                          metadata=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `currency` | [`Currency`](../../doc/models/currency.md) | Query, Optional | The currency associated with the internal account. |
| `counterparty_id` | `str` | Query, Optional | The counterparty associated with the internal account. |
| `payment_type` | [`PaymentType13`](../../doc/models/payment-type-13.md) | Query, Optional | The type of payment that can be made by the internal account. |
| `payment_direction` | [`PaymentDirection`](../../doc/models/payment-direction.md) | Query, Optional | The direction of payments that can be made by internal account. |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[InternalAccount]`](../../doc/models/internal-account.md).

## Example Usage

```python
result = internal_account_controller.list_internal_accounts()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Internal Account

```python
def create_internal_account(self,
                           idempotency_key=None,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`InternalAccountCreateRequest`](../../doc/models/internal-account-create-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`InternalAccount`](../../doc/models/internal-account.md).

## Example Usage

```python
body = InternalAccountCreateRequest(
    connection_id='connection_id6',
    name='name6',
    party_name='party_name8',
    currency=Currency1.USD,
    vendor_attributes={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = internal_account_controller.create_internal_account(
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


# Get Internal Account

```python
def get_internal_account(self,
                        id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | Unique identifier for the account. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`InternalAccount`](../../doc/models/internal-account.md).

## Example Usage

```python
id = 'id0'

result = internal_account_controller.get_internal_account(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Internal Account

```python
def update_internal_account(self,
                           id,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | Unique identifier for the account. |
| `body` | [`InternalAccountUpdateRequest`](../../doc/models/internal-account-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`InternalAccount`](../../doc/models/internal-account.md).

## Example Usage

```python
id = 'id0'

result = internal_account_controller.update_internal_account(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


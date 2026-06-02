# Ledger Account Payout

```python
ledger_account_payout_controller = client.ledger_account_payout
```

## Class Name

`LedgerAccountPayoutController`

## Methods

* [Create Ledger Account Payout](../../doc/controllers/ledger-account-payout.md#create-ledger-account-payout)
* [List Ledger Account Payouts](../../doc/controllers/ledger-account-payout.md#list-ledger-account-payouts)
* [Get Ledger Account Payout](../../doc/controllers/ledger-account-payout.md#get-ledger-account-payout)
* [Update Ledger Account Payout](../../doc/controllers/ledger-account-payout.md#update-ledger-account-payout)


# Create Ledger Account Payout

Create a ledger account payout.

```python
def create_ledger_account_payout(self,
                                idempotency_key=None,
                                body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`LedgerAccountPayoutCreateRequest`](../../doc/models/ledger-account-payout-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerAccountPayout`](../../doc/models/ledger-account-payout.md).

## Example Usage

```python
body = LedgerAccountPayoutCreateRequest(
    payout_ledger_account_id='000010e0-0000-0000-0000-000000000000',
    funding_ledger_account_id='00000298-0000-0000-0000-000000000000',
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_account_payout_controller.create_ledger_account_payout(
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
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# List Ledger Account Payouts

Get a list of ledger account payouts.

```python
def list_ledger_account_payouts(self,
                               after_cursor=None,
                               per_page=None,
                               metadata=None,
                               payout_ledger_account_id=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `payout_ledger_account_id` | `str` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[LedgerAccountPayout]`](../../doc/models/ledger-account-payout.md).

## Example Usage

```python
result = ledger_account_payout_controller.list_ledger_account_payouts()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Get Ledger Account Payout

Get details on a single ledger account payout.

```python
def get_ledger_account_payout(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerAccountPayout`](../../doc/models/ledger-account-payout.md).

## Example Usage

```python
id = 'id0'

result = ledger_account_payout_controller.get_ledger_account_payout(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Ledger Account Payout

Update the details of a ledger account payout.

```python
def update_ledger_account_payout(self,
                                id,
                                body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `body` | [`LedgerAccountPayoutUpdateRequest`](../../doc/models/ledger-account-payout-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`LedgerAccountPayout`](../../doc/models/ledger-account-payout.md).

## Example Usage

```python
id = 'id0'

body = LedgerAccountPayoutUpdateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_account_payout_controller.update_ledger_account_payout(
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
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


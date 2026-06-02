# Account Detail

```python
account_detail_api = client.account_detail
```

## Class Name

`AccountDetailApi`

## Methods

* [List Account Details](../../doc/controllers/account-detail.md#list-account-details)
* [Create Account Detail](../../doc/controllers/account-detail.md#create-account-detail)
* [Get Account Detail](../../doc/controllers/account-detail.md#get-account-detail)
* [Delete Account Detail](../../doc/controllers/account-detail.md#delete-account-detail)


# List Account Details

Get a list of account details for a single internal or external account.

```python
def list_account_details(self,
                        accounts_type,
                        account_id,
                        after_cursor=None,
                        per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accounts_type` | [`AccountsType`](../../doc/models/accounts-type.md) | Template, Required | - |
| `account_id` | `str` | Template, Required | The ID of the account. |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[AccountDetail]`](../../doc/models/account-detail.md).

## Example Usage

```python
accounts_type = AccountsType.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

result = account_detail_api.list_account_details(
    accounts_type,
    account_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Account Detail

Create an account detail for an external account.

```python
def create_account_detail(self,
                         accounts_type,
                         account_id,
                         idempotency_key=None,
                         body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accounts_type` | [`AccountsType1`](../../doc/models/accounts-type-1.md) | Template, Required | - |
| `account_id` | `str` | Template, Required | The ID of the account. |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`AccountDetailCreateRequest`](../../doc/models/account-detail-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AccountDetail`](../../doc/models/account-detail.md).

## Example Usage

```python
accounts_type = AccountsType1.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

result = account_detail_api.create_account_detail(
    accounts_type,
    account_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Account Detail

Get a single account detail for a single internal or external account.

```python
def get_account_detail(self,
                      accounts_type,
                      account_id,
                      id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accounts_type` | [`AccountsType`](../../doc/models/accounts-type.md) | Template, Required | - |
| `account_id` | `str` | Template, Required | The ID of the account. |
| `id` | `str` | Template, Required | The ID of the account detail. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AccountDetail`](../../doc/models/account-detail.md).

## Example Usage

```python
accounts_type = AccountsType.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

id = 'id0'

result = account_detail_api.get_account_detail(
    accounts_type,
    account_id,
    id
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


# Delete Account Detail

Delete a single account detail for an external account.

```python
def delete_account_detail(self,
                         accounts_type,
                         account_id,
                         id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accounts_type` | [`AccountsType1`](../../doc/models/accounts-type-1.md) | Template, Required | - |
| `account_id` | `str` | Template, Required | The ID of the account. |
| `id` | `str` | Template, Required | The ID of the account detail. |

## Response Type

**204**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
accounts_type = AccountsType1.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

id = 'id0'

result = account_detail_api.delete_account_detail(
    accounts_type,
    account_id,
    id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


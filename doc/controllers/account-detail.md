# Account Detail

```python
account_detail_controller = client.account_detail
```

## Class Name

`AccountDetailController`

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
| `accounts_type` | [`AccountsTypeEnum`](../../doc/models/accounts-type-enum.md) | Template, Required | - |
| `account_id` | `str` | Template, Required | The ID of the account. |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

[`List[AccountDetail]`](../../doc/models/account-detail.md)

## Example Usage

```python
accounts_type = AccountsTypeEnum.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

result = account_detail_controller.list_account_details(
    accounts_type,
    account_id
)
print(result)
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
| `accounts_type` | [`AccountsType1Enum`](../../doc/models/accounts-type-1-enum.md) | Template, Required | - |
| `account_id` | `str` | Template, Required | The ID of the account. |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`AccountDetailCreateRequest`](../../doc/models/account-detail-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

[`AccountDetail`](../../doc/models/account-detail.md)

## Example Usage

```python
accounts_type = AccountsType1Enum.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

result = account_detail_controller.create_account_detail(
    accounts_type,
    account_id
)
print(result)
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
| `accounts_type` | [`AccountsTypeEnum`](../../doc/models/accounts-type-enum.md) | Template, Required | - |
| `account_id` | `str` | Template, Required | The ID of the account. |
| `id` | `str` | Template, Required | The ID of the account detail. |

## Response Type

**200**: successful

[`AccountDetail`](../../doc/models/account-detail.md)

## Example Usage

```python
accounts_type = AccountsTypeEnum.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

id = 'id0'

result = account_detail_controller.get_account_detail(
    accounts_type,
    account_id,
    id
)
print(result)
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
| `accounts_type` | [`AccountsType1Enum`](../../doc/models/accounts-type-1-enum.md) | Template, Required | - |
| `account_id` | `str` | Template, Required | The ID of the account. |
| `id` | `str` | Template, Required | The ID of the account detail. |

## Response Type

**204**: successful

`void`

## Example Usage

```python
accounts_type = AccountsType1Enum.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

id = 'id0'

account_detail_controller.delete_account_detail(
    accounts_type,
    account_id,
    id
)
```


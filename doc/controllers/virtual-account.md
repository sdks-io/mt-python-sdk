# Virtual Account

```python
virtual_account_controller = client.virtual_account
```

## Class Name

`VirtualAccountController`

## Methods

* [List Virtual Accounts](../../doc/controllers/virtual-account.md#list-virtual-accounts)
* [Create Virtual Account](../../doc/controllers/virtual-account.md#create-virtual-account)
* [Get Virtual Account](../../doc/controllers/virtual-account.md#get-virtual-account)
* [Update Virtual Account](../../doc/controllers/virtual-account.md#update-virtual-account)
* [Delete Virtual Account](../../doc/controllers/virtual-account.md#delete-virtual-account)


# List Virtual Accounts

Get a list of virtual accounts.

```python
def list_virtual_accounts(self,
                         after_cursor=None,
                         per_page=None,
                         internal_account_id=None,
                         counterparty_id=None,
                         metadata=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `internal_account_id` | `uuid\|str` | Query, Optional | - |
| `counterparty_id` | `uuid\|str` | Query, Optional | - |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |

## Response Type

**200**: successful

[`List[VirtualAccount]`](../../doc/models/virtual-account.md)

## Example Usage

```python
result = virtual_account_controller.list_virtual_accounts()
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create Virtual Account

```python
def create_virtual_account(self,
                          idempotency_key=None,
                          body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`VirtualAccountCreateRequest`](../../doc/models/virtual-account-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

[`VirtualAccount`](../../doc/models/virtual-account.md)

## Example Usage

```python
result = virtual_account_controller.create_virtual_account()
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | unauthorized | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Virtual Account

```python
def get_virtual_account(self,
                       id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | Virtual Acccount ID |

## Response Type

**200**: successful

[`VirtualAccount`](../../doc/models/virtual-account.md)

## Example Usage

```python
id = 'id0'

result = virtual_account_controller.get_virtual_account(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Virtual Account

```python
def update_virtual_account(self,
                          id,
                          body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | Virtual Acccount ID |
| `body` | [`VirtualAccountUpdateRequest`](../../doc/models/virtual-account-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

[`VirtualAccount`](../../doc/models/virtual-account.md)

## Example Usage

```python
id = 'id0'

result = virtual_account_controller.update_virtual_account(id)
print(result)
```


# Delete Virtual Account

```python
def delete_virtual_account(self,
                          id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | Virtual Acccount ID |

## Response Type

**200**: successful

[`VirtualAccount`](../../doc/models/virtual-account.md)

## Example Usage

```python
id = 'id0'

result = virtual_account_controller.delete_virtual_account(id)
print(result)
```


# External Account

```python
external_account_controller = client.external_account
```

## Class Name

`ExternalAccountController`

## Methods

* [Verify External Account](../../doc/controllers/external-account.md#verify-external-account)
* [Complete Verification External Account](../../doc/controllers/external-account.md#complete-verification-external-account)
* [List External Accounts](../../doc/controllers/external-account.md#list-external-accounts)
* [Create External Account](../../doc/controllers/external-account.md#create-external-account)
* [Get External Account](../../doc/controllers/external-account.md#get-external-account)
* [Update External Account](../../doc/controllers/external-account.md#update-external-account)
* [Delete External Account](../../doc/controllers/external-account.md#delete-external-account)


# Verify External Account

```python
def verify_external_account(self,
                           id,
                           idempotency_key=None,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | external account id |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`ExternalAccountVerifyRequest`](../../doc/models/external-account-verify-request.md) | Body, Optional | - |

## Response Type

**200**: successful

[`ExternalAccount`](../../doc/models/external-account.md)

## Example Usage

```python
id = 'id0'

result = external_account_controller.verify_external_account(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Complete Verification External Account

```python
def complete_verification_external_account(self,
                                          id,
                                          idempotency_key=None,
                                          body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | external account id |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`ExternalAccountCompleteVerificationRequest`](../../doc/models/external-account-complete-verification-request.md) | Body, Optional | - |

## Response Type

**200**: successful

[`ExternalAccount`](../../doc/models/external-account.md)

## Example Usage

```python
id = 'id0'

body = ExternalAccountCompleteVerificationRequest(
    amounts=[
        2,
        4
    ]
)

result = external_account_controller.complete_verification_external_account(
    id,
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# List External Accounts

```python
def list_external_accounts(self,
                          after_cursor=None,
                          per_page=None,
                          party_name=None,
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
| `party_name` | `str` | Query, Optional | Searches the ExternalAccount's party_name AND the Counterparty's party_name |
| `counterparty_id` | `str` | Query, Optional | - |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |

## Response Type

**200**: successful

[`List[ExternalAccount]`](../../doc/models/external-account.md)

## Example Usage

```python
result = external_account_controller.list_external_accounts()
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create External Account

```python
def create_external_account(self,
                           idempotency_key=None,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`ExternalAccountCreateRequest`](../../doc/models/external-account-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

[`ExternalAccount`](../../doc/models/external-account.md)

## Example Usage

```python
body = ExternalAccountCreateRequest(
    counterparty_id='00000a30-0000-0000-0000-000000000000',
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = external_account_controller.create_external_account(
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get External Account

```python
def get_external_account(self,
                        id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | external account id |

## Response Type

**200**: successful

[`ExternalAccount`](../../doc/models/external-account.md)

## Example Usage

```python
id = 'id0'

result = external_account_controller.get_external_account(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update External Account

```python
def update_external_account(self,
                           id,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | external account id |
| `body` | [`ExternalAccountUpdateRequest`](../../doc/models/external-account-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

[`ExternalAccount`](../../doc/models/external-account.md)

## Example Usage

```python
id = 'id0'

result = external_account_controller.update_external_account(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Delete External Account

```python
def delete_external_account(self,
                           id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | external account id |

## Response Type

**204**: successful

`void`

## Example Usage

```python
id = 'id0'

external_account_controller.delete_external_account(id)
```


# Account Collection Flow

```python
account_collection_flow_controller = client.account_collection_flow
```

## Class Name

`AccountCollectionFlowController`

## Methods

* [List Account Collection Flows](../../doc/controllers/account-collection-flow.md#list-account-collection-flows)
* [Create Account Collection Flow](../../doc/controllers/account-collection-flow.md#create-account-collection-flow)
* [Get Account Collection Flow](../../doc/controllers/account-collection-flow.md#get-account-collection-flow)
* [Update Account Collection Flow](../../doc/controllers/account-collection-flow.md#update-account-collection-flow)


# List Account Collection Flows

```python
def list_account_collection_flows(self,
                                 after_cursor=None,
                                 per_page=None,
                                 client_token=None,
                                 status=None,
                                 counterparty_id=None,
                                 external_account_id=None)
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
| `external_account_id` | `str` | Query, Optional | - |

## Response Type

**200**: successful

[`List[AccountCollectionFlow]`](../../doc/models/account-collection-flow.md)

## Example Usage

```python
result = account_collection_flow_controller.list_account_collection_flows()
print(result)
```


# Create Account Collection Flow

```python
def create_account_collection_flow(self,
                                  idempotency_key=None,
                                  body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`AccountCollectionFlowCreateRequest`](../../doc/models/account-collection-flow-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

[`AccountCollectionFlow`](../../doc/models/account-collection-flow.md)

## Example Usage

```python
result = account_collection_flow_controller.create_account_collection_flow()
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Account Collection Flow

```python
def get_account_collection_flow(self,
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

[`AccountCollectionFlow`](../../doc/models/account-collection-flow.md)

## Example Usage

```python
id = 'id0'

result = account_collection_flow_controller.get_account_collection_flow(id)
print(result)
```


# Update Account Collection Flow

```python
def update_account_collection_flow(self,
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
| `body` | [`AccountCollectionFlowUpdateRequest`](../../doc/models/account-collection-flow-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

[`AccountCollectionFlow`](../../doc/models/account-collection-flow.md)

## Example Usage

```python
id = 'id0'

body = AccountCollectionFlowUpdateRequest()

result = account_collection_flow_controller.update_account_collection_flow(
    id,
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


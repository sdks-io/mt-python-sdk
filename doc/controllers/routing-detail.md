# Routing Detail

```python
routing_detail_api = client.routing_detail
```

## Class Name

`RoutingDetailApi`

## Methods

* [List Routing Details](../../doc/controllers/routing-detail.md#list-routing-details)
* [Create Routing Detail](../../doc/controllers/routing-detail.md#create-routing-detail)
* [Get Routing Detail](../../doc/controllers/routing-detail.md#get-routing-detail)
* [Delete Routing Detail](../../doc/controllers/routing-detail.md#delete-routing-detail)


# List Routing Details

Get a list of routing details for a single internal or external account.

```python
def list_routing_details(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[RoutingDetail]`](../../doc/models/routing-detail.md).

## Example Usage

```python
accounts_type = AccountsType.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

result = routing_detail_api.list_routing_details(
    accounts_type,
    account_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Routing Detail

Create a routing detail for a single external account.

```python
def create_routing_detail(self,
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
| `body` | [`RoutingDetailCreateRequest`](../../doc/models/routing-detail-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RoutingDetail`](../../doc/models/routing-detail.md).

## Example Usage

```python
accounts_type = AccountsType1.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

result = routing_detail_api.create_routing_detail(
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


# Get Routing Detail

Get a single routing detail for a single internal or external account.

```python
def get_routing_detail(self,
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
| `id` | `str` | Template, Required | The ID of the routing detail. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RoutingDetail`](../../doc/models/routing-detail.md).

## Example Usage

```python
accounts_type = AccountsType.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

id = 'id0'

result = routing_detail_api.get_routing_detail(
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


# Delete Routing Detail

Delete a routing detail for a single external account.

```python
def delete_routing_detail(self,
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
| `id` | `str` | Template, Required | The ID of the routing detail. |

## Response Type

**204**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
accounts_type = AccountsType1.EXTERNAL_ACCOUNTS

account_id = 'account_id2'

id = 'id0'

result = routing_detail_api.delete_routing_detail(
    accounts_type,
    account_id,
    id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


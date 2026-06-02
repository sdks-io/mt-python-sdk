# Counterparty

```python
counterparty_api = client.counterparty
```

## Class Name

`CounterpartyApi`

## Methods

* [Collect Account Details](../../doc/controllers/counterparty.md#collect-account-details)
* [List Counterparties](../../doc/controllers/counterparty.md#list-counterparties)
* [Create Counterparty](../../doc/controllers/counterparty.md#create-counterparty)
* [Get Counterparty](../../doc/controllers/counterparty.md#get-counterparty)
* [Update Counterparty](../../doc/controllers/counterparty.md#update-counterparty)
* [Delete Counterparty](../../doc/controllers/counterparty.md#delete-counterparty)


# Collect Account Details

Send an email requesting account details.

```python
def collect_account_details(self,
                           id,
                           idempotency_key=None,
                           body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | counterparty id |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`CounterpartyCollectAccountRequest`](../../doc/models/counterparty-collect-account-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`CounterpartyCollectAccountResponse`](../../doc/models/counterparty-collect-account-response.md).

## Example Usage

```python
id = 'id0'

result = counterparty_api.collect_account_details(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# List Counterparties

Get a paginated list of all counterparties.

```python
def list_counterparties(self,
                       after_cursor=None,
                       per_page=None,
                       name=None,
                       email=None,
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
| `name` | `str` | Query, Optional | Performs a partial string match of the name field. This is also case insensitive. |
| `email` | `str` | Query, Optional | Performs a partial string match of the email field. This is also case insensitive. |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `created_at_lower_bound` | `datetime` | Query, Optional | Used to return counterparties created after some datetime. |
| `created_at_upper_bound` | `datetime` | Query, Optional | Used to return counterparties created before some datetime. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[Counterparty]`](../../doc/models/counterparty.md).

## Example Usage

```python
result = counterparty_api.list_counterparties()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad_request | `ApiException` |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create Counterparty

Create a new counterparty.

```python
def create_counterparty(self,
                       idempotency_key=None,
                       body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`CounterpartyCreateRequest`](../../doc/models/counterparty-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Counterparty`](../../doc/models/counterparty.md).

## Example Usage

```python
body = CounterpartyCreateRequest(
    name='name6',
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = counterparty_api.create_counterparty(
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
| 415 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Counterparty

Get details on a single counterparty.

```python
def get_counterparty(self,
                    id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | The id of an existing counterparty. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Counterparty`](../../doc/models/counterparty.md).

## Example Usage

```python
id = 'id0'

result = counterparty_api.get_counterparty(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Counterparty

Updates a given counterparty with new information.

```python
def update_counterparty(self,
                       id,
                       body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | The id of an existing counterparty. |
| `body` | [`CounterpartyUpdateRequest`](../../doc/models/counterparty-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Counterparty`](../../doc/models/counterparty.md).

## Example Usage

```python
id = 'id0'

result = counterparty_api.update_counterparty(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Delete Counterparty

Deletes a given counterparty.

```python
def delete_counterparty(self,
                       id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | The id of an existing counterparty. |

## Response Type

**204**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
id = 'id0'

result = counterparty_api.delete_counterparty(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


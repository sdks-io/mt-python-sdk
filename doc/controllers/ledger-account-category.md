# Ledger Account Category

```python
ledger_account_category_controller = client.ledger_account_category
```

## Class Name

`LedgerAccountCategoryController`

## Methods

* [List Ledger Account Categories](../../doc/controllers/ledger-account-category.md#list-ledger-account-categories)
* [Create Ledger Account Category](../../doc/controllers/ledger-account-category.md#create-ledger-account-category)
* [Get Ledger Account Category](../../doc/controllers/ledger-account-category.md#get-ledger-account-category)
* [Update Ledger Account Category](../../doc/controllers/ledger-account-category.md#update-ledger-account-category)
* [Delete Ledger Account Category](../../doc/controllers/ledger-account-category.md#delete-ledger-account-category)
* [Add Ledger Account to Ledger Account Category](../../doc/controllers/ledger-account-category.md#add-ledger-account-to-ledger-account-category)
* [Remove Ledger Account from Ledger Account Category](../../doc/controllers/ledger-account-category.md#remove-ledger-account-from-ledger-account-category)
* [Add Ledger Account Category to Ledger Account Category](../../doc/controllers/ledger-account-category.md#add-ledger-account-category-to-ledger-account-category)
* [Delete Ledger Account Category from Ledger Account Category](../../doc/controllers/ledger-account-category.md#delete-ledger-account-category-from-ledger-account-category)


# List Ledger Account Categories

Get a list of ledger account categories.

```python
def list_ledger_account_categories(self,
                                  after_cursor=None,
                                  per_page=None,
                                  metadata=None,
                                  name=None,
                                  ledger_id=None,
                                  parent_ledger_account_category_id=None,
                                  ledger_account_id=None,
                                  balances=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |
| `name` | `str` | Query, Optional | - |
| `ledger_id` | `str` | Query, Optional | - |
| `parent_ledger_account_category_id` | `str` | Query, Optional | Query categories that are nested underneath a parent category |
| `ledger_account_id` | `str` | Query, Optional | Query categories which contain a ledger account directly or through child categories. |
| `balances` | [`Balances`](../../doc/models/balances.md) | Query, Optional | For example, if you want the balances as of a particular time (ISO8601), the encoded query string would be `balances%5Beffective_at%5D=2000-12-31T12:00:00Z`. The balances as of a time are inclusive of entries with that exact time. |

## Response Type

**200**: successful

[`List[LedgerAccountCategory]`](../../doc/models/ledger-account-category.md)

## Example Usage

```python
result = ledger_account_category_controller.list_ledger_account_categories()
print(result)
```


# Create Ledger Account Category

Create a ledger account category.

```python
def create_ledger_account_category(self,
                                  idempotency_key=None,
                                  body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`LedgerAccountCategoryCreateRequest`](../../doc/models/ledger-account-category-create-request.md) | Body, Optional | - |

## Response Type

**201**: successful

[`LedgerAccountCategory`](../../doc/models/ledger-account-category.md)

## Example Usage

```python
body = LedgerAccountCategoryCreateRequest(
    name='name6',
    currency='currency6',
    ledger_id='00002576-0000-0000-0000-000000000000',
    normal_balance=NormalBalance2Enum.CREDIT,
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_account_category_controller.create_ledger_account_category(
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Ledger Account Category

Get the details on a single ledger account category.

```python
def get_ledger_account_category(self,
                               id,
                               balances=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `balances` | [`Balances1`](../../doc/models/balances-1.md) | Query, Optional | For example, if you want the balances as of a particular time (ISO8601), the encoded query string would be `balances%5Beffective_at%5D=2000-12-31T12:00:00Z`. The balances as of a time are inclusive of entries with that exact time. |

## Response Type

**200**: successful

[`LedgerAccountCategory`](../../doc/models/ledger-account-category.md)

## Example Usage

```python
id = 'id0'

result = ledger_account_category_controller.get_ledger_account_category(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Ledger Account Category

Update the details of a ledger account category.

```python
def update_ledger_account_category(self,
                                  id,
                                  body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `body` | [`LedgerAccountCategoryUpdateRequest`](../../doc/models/ledger-account-category-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

[`LedgerAccountCategory`](../../doc/models/ledger-account-category.md)

## Example Usage

```python
id = 'id0'

body = LedgerAccountCategoryUpdateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = ledger_account_category_controller.update_ledger_account_category(
    id,
    body=body
)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Delete Ledger Account Category

Delete a ledger account category.

```python
def delete_ledger_account_category(self,
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

[`LedgerAccountCategory`](../../doc/models/ledger-account-category.md)

## Example Usage

```python
id = 'id0'

result = ledger_account_category_controller.delete_ledger_account_category(id)
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Add Ledger Account to Ledger Account Category

Add a ledger account to a ledger account category.

```python
def add_ledger_account_to_ledger_account_category(self,
                                                 id,
                                                 ledger_account_id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `ledger_account_id` | `str` | Template, Required | ledger_account_id |

## Response Type

**200**: successful

`void`

## Example Usage

```python
id = 'id0'

ledger_account_id = 'ledger_account_id4'

ledger_account_category_controller.add_ledger_account_to_ledger_account_category(
    id,
    ledger_account_id
)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Remove Ledger Account from Ledger Account Category

Remove a ledger account from a ledger account category.

```python
def remove_ledger_account_from_ledger_account_category(self,
                                                      id,
                                                      ledger_account_id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `ledger_account_id` | `str` | Template, Required | ledger_account_id |

## Response Type

**200**: successful

`void`

## Example Usage

```python
id = 'id0'

ledger_account_id = 'ledger_account_id4'

ledger_account_category_controller.remove_ledger_account_from_ledger_account_category(
    id,
    ledger_account_id
)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Add Ledger Account Category to Ledger Account Category

Add a ledger account category to a ledger account category.

```python
def add_ledger_account_category_to_ledger_account_category(self,
                                                          id,
                                                          sub_category_id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `sub_category_id` | `str` | Template, Required | sub_category_id |

## Response Type

**200**: successful

`void`

## Example Usage

```python
id = 'id0'

sub_category_id = 'sub_category_id0'

ledger_account_category_controller.add_ledger_account_category_to_ledger_account_category(
    id,
    sub_category_id
)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Delete Ledger Account Category from Ledger Account Category

Delete a ledger account category from a ledger account category.

```python
def delete_ledger_account_category_from_ledger_account_category(self,
                                                               id,
                                                               sub_category_id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | id |
| `sub_category_id` | `str` | Template, Required | sub_category_id |

## Response Type

**200**: successful

`void`

## Example Usage

```python
id = 'id0'

sub_category_id = 'sub_category_id0'

ledger_account_category_controller.delete_ledger_account_category_from_ledger_account_category(
    id,
    sub_category_id
)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


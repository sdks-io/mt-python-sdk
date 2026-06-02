# Paper Item

```python
paper_item_api = client.paper_item
```

## Class Name

`PaperItemApi`

## Methods

* [List Paper Items](../../doc/controllers/paper-item.md#list-paper-items)
* [Get Paper Item](../../doc/controllers/paper-item.md#get-paper-item)


# List Paper Items

Get a list of all paper items.

```python
def list_paper_items(self,
                    lockbox_number=None,
                    deposit_date_start=None,
                    deposit_date_end=None,
                    after_cursor=None,
                    per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `lockbox_number` | `str` | Query, Optional | Specify `lockbox_number` if you wish to see paper items that are associated with a specific lockbox number. |
| `deposit_date_start` | `date` | Query, Optional | Specify an inclusive start date (YYYY-MM-DD) when filtering by deposit_date |
| `deposit_date_end` | `date` | Query, Optional | Specify an inclusive end date (YYYY-MM-DD) when filtering by deposit_date |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[PaperItem]`](../../doc/models/paper-item.md).

## Example Usage

```python
result = paper_item_api.list_paper_items()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Get Paper Item

Get details on a single paper item.

```python
def get_paper_item(self,
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PaperItem`](../../doc/models/paper-item.md).

## Example Usage

```python
id = 'id0'

result = paper_item_api.get_paper_item(id)

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


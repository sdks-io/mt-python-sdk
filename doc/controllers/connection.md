# Connection

```python
connection_controller = client.connection
```

## Class Name

`ConnectionController`


# List Connections

Get a list of all connections.

```python
def list_connections(self,
                    after_cursor=None,
                    per_page=None,
                    vendor_customer_id=None,
                    entity=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `vendor_customer_id` | `uuid\|str` | Query, Optional | An identifier assigned by the vendor to your organization. |
| `entity` | `str` | Query, Optional | A string code representing the vendor (i.e. bank). |

## Response Type

**200**: successful

[`List[Connection]`](../../doc/models/connection.md)

## Example Usage

```python
result = connection_controller.list_connections()
print(result)
```


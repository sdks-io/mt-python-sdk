
# Errors

*This model accepts additional fields of type Any.*

## Structure

`Errors`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | [`Code`](../../doc/models/code.md) | Optional | - |
| `message` | `str` | Optional | - |
| `parameter` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "code": "resource_not_found",
  "message": "message6",
  "parameter": "parameter0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


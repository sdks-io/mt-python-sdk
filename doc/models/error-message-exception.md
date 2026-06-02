
# Error Message Exception

*This model accepts additional fields of type Any.*

## Structure

`ErrorMessageException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `errors` | [`Errors`](../../doc/models/errors.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "errors": {
    "code": "expired_key",
    "message": "message0",
    "parameter": "parameter6",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


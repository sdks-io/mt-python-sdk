
# Account Collection Flow Update Request

*This model accepts additional fields of type Any.*

## Structure

`AccountCollectionFlowUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `str` | Required, Constant | Required. The updated status of the account collection flow. Can only be used to mark a flow as `cancelled`.<br><br>**Value**: `"cancelled"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "status": "cancelled",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


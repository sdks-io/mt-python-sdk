
# External Account Complete Verification Request

*This model accepts additional fields of type Any.*

## Structure

`ExternalAccountCompleteVerificationRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amounts` | `List[int]` | Optional | **Constraints**: *Maximum Items*: `2` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "amounts": [
    2,
    4
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


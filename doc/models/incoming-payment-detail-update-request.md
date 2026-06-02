
# Incoming Payment Detail Update Request

*This model accepts additional fields of type Any.*

## Structure

`IncomingPaymentDetailUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `metadata` | `Dict[str, str]` | Optional | Additional data in the form of key-value pairs. Pairs can be removed by passing an empty string or `null` as the value. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "metadata": {
    "key0": "metadata7",
    "key1": "metadata6"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


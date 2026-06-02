
# Accounting 1

*This model accepts additional fields of type Any.*

## Structure

`Accounting1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | [`Type`](../../doc/models/type.md) | Optional | An optional type to auto-sync the counterparty to your ledger. Either `customer` or `vendor`. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "type": "customer",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


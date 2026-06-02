
# Ledger Account Update Request

*This model accepts additional fields of type Any.*

## Structure

`LedgerAccountUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Optional | The name of the ledger account. |
| `description` | `str` | Optional | The description of the ledger account. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "name": "name8",
  "description": "description2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


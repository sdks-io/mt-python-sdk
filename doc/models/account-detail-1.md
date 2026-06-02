
# Account Detail 1

*This model accepts additional fields of type Any.*

## Structure

`AccountDetail1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_number` | `str` | Required | - |
| `account_number_type` | [`AccountNumberType2`](../../doc/models/account-number-type-2.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_number": "account_number8",
  "account_number_type": "other",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


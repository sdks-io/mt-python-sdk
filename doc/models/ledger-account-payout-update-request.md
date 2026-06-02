
# Ledger Account Payout Update Request

*This model accepts additional fields of type Any.*

## Structure

`LedgerAccountPayoutUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `description` | `str` | Optional | The description of the ledger account payout. |
| `status` | [`Status8`](../../doc/models/status-8.md) | Optional | To post a pending ledger account payout, use `posted`. To archive a pending ledger transaction, use `archived`. |
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
  "description": "description6",
  "status": "posted",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


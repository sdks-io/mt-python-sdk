
# Ledger Account Payout Update Request

## Structure

`LedgerAccountPayoutUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `description` | `str` | Optional | The description of the ledger account payout. |
| `status` | [`Status8Enum`](../../doc/models/status-8-enum.md) | Optional | To post a pending ledger account payout, use `posted`. To archive a pending ledger transaction, use `archived`. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |

## Example (as JSON)

```json
{
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "description": "description6",
  "status": "posted"
}
```


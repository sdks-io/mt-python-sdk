
# Ledger Transaction Reversal Create Request

## Structure

`LedgerTransactionReversalCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `description` | `str` | Optional | An optional free-form description for the reversal ledger transaction. Maximum of 1000 characters allowed. |
| `status` | [`Status15Enum`](../../doc/models/status-15-enum.md) | Optional | Status of the reversal ledger transaction. It defaults to `posted` if not provided. |
| `metadata` | `Dict[str, str]` | Optional | Additional data to be added to the reversal ledger transaction as key-value pairs. Both the key and value must be strings. |
| `effective_at` | `datetime` | Optional | The timestamp (ISO8601 format) at which the reversal ledger transaction happened for reporting purposes. It defaults to the `effective_at` of the original ledger transaction if not provided. |
| `external_id` | `str` | Optional | Must be unique within the ledger. |
| `ledgerable_type` | [`LedgerableType5Enum`](../../doc/models/ledgerable-type-5-enum.md) | Optional | Specify this if you'd like to link the reversal ledger transaction to a Payment object like Return or Reversal. |
| `ledgerable_id` | `uuid\|str` | Optional | Specify this if you'd like to link the reversal ledger transaction to a Payment object like Return or Reversal. |

## Example (as JSON)

```json
{
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "description": "description6",
  "status": "archived",
  "effective_at": "2016-03-13T12:52:32.123Z",
  "external_id": "external_id2"
}
```


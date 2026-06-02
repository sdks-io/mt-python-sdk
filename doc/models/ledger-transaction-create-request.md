
# Ledger Transaction Create Request

## Structure

`LedgerTransactionCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `description` | `str` | Optional | An optional description for internal use. |
| `status` | [`Status11Enum`](../../doc/models/status-11-enum.md) | Optional | To post a ledger transaction at creation, use `posted`. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `effective_at` | `date` | Optional | The timestamp (ISO8601 format) at which the ledger transaction happened for reporting purposes. |
| `effective_date` | `date` | Optional | The date (YYYY-MM-DD) on which the ledger transaction happened for reporting purposes. |
| `ledger_entries` | [`List[LedgerEntryCreateRequest]`](../../doc/models/ledger-entry-create-request.md) | Required | An array of ledger entry objects. |
| `external_id` | `str` | Optional | A unique string to represent the ledger transaction. Only one pending or posted ledger transaction may have this ID in the ledger. |
| `ledgerable_type` | [`LedgerableType2Enum`](../../doc/models/ledgerable-type-2-enum.md) | Optional | If the ledger transaction can be reconciled to another object in Modern Treasury, the type will be populated here, otherwise null. This can be one of payment_order, incoming_payment_detail, expected_payment, return, or reversal. |
| `ledgerable_id` | `uuid\|str` | Optional | If the ledger transaction can be reconciled to another object in Modern Treasury, the id will be populated here, otherwise null. |

## Example (as JSON)

```json
{
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "ledger_entries": [
    {
      "amount": 60,
      "direction": "credit",
      "ledger_account_id": "00002600-0000-0000-0000-000000000000",
      "metadata": {
        "key": "value",
        "foo": "bar",
        "modern": "treasury"
      },
      "lock_version": 14,
      "pending_balance_amount": {
        "key0": 246,
        "key1": 247,
        "key2": 248
      },
      "posted_balance_amount": {
        "key0": 238,
        "key1": 239
      },
      "available_balance_amount": {
        "key0": 187,
        "key1": 188,
        "key2": 189
      },
      "show_resulting_ledger_account_balances": false
    }
  ],
  "description": "description6",
  "status": "archived",
  "effective_at": "2016-03-13",
  "effective_date": "2016-03-13"
}
```


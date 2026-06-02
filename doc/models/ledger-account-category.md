
# Ledger Account Category

## Structure

`LedgerAccountCategory`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `discarded_at` | `datetime` | Required | - |
| `name` | `str` | Required | The name of the ledger account category. |
| `description` | `str` | Required | The description of the ledger account category. |
| `metadata` | `Dict[str, str]` | Required | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `ledger_id` | `uuid\|str` | Required | The id of the ledger that this account category belongs to. |
| `normal_balance` | [`NormalBalance2Enum`](../../doc/models/normal-balance-2-enum.md) | Required | The normal balance of the ledger account category. |
| `balances` | [`LedgerBalances`](../../doc/models/ledger-balances.md) | Required | - |

## Example (as JSON)

```json
{
  "id": "00000682-0000-0000-0000-000000000000",
  "object": "object4",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "discarded_at": "2016-03-13T12:52:32.123Z",
  "name": "name6",
  "description": "description6",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "ledger_id": "00000690-0000-0000-0000-000000000000",
  "normal_balance": "credit",
  "balances": {
    "pending_balance": {
      "credits": 144,
      "debits": 148,
      "amount": 30,
      "currency": "currency8",
      "currency_exponent": 148
    },
    "posted_balance": {
      "credits": 156,
      "debits": 136,
      "amount": 18,
      "currency": "currency8",
      "currency_exponent": 160
    },
    "available_balance": {
      "credits": 108,
      "debits": 184,
      "amount": 66,
      "currency": "currency2",
      "currency_exponent": 112
    }
  }
}
```



# Ledger Entry of Transaction Version

## Structure

`LedgerEntryOfTransactionVersion`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `amount` | `int` | Required | Value in specified currency's smallest unit. e.g. $10 would be represented as 1000. Can be any integer up to 36 digits. |
| `direction` | [`Direction5`](../../doc/models/direction-5.md) | Required | One of `credit`, `debit`. Describes the direction money is flowing in the transaction. A `credit` moves money from your account to someone else's. A `debit` pulls money from someone else's account to your own. Note that wire, rtp, and check payments will always be `credit`. |
| `status` | [`Status9`](../../doc/models/status-9.md) | Required | Equal to the state of the ledger transaction when the ledger entry was created. One of `pending`, `posted`, or `archived`. |
| `ledger_account_id` | `uuid\|str` | Required | The ledger account that this ledger entry is associated with. |
| `ledger_account_lock_version` | `int` | Required | Lock version of the ledger account. This can be passed when creating a ledger transaction to only succeed if no ledger transactions have posted since the given version. See our post about Designing the Ledgers API with Optimistic Locking for more details. |
| `ledger_account_currency` | `str` | Required | The currency of the ledger account. |
| `ledger_account_currency_exponent` | `int` | Required | The currency exponent of the ledger account. |
| `ledger_transaction_id` | `str` | Required | The ledger transaction that this ledger entry is associated with. |
| `metadata` | `Dict[str, str]` | Required | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `resulting_ledger_account_balances` | [`LedgerBalances`](../../doc/models/ledger-balances.md) | Required | - |

## Example (as JSON)

```json
{
  "id": "00000624-0000-0000-0000-000000000000",
  "object": "object0",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "amount": 106,
  "direction": "credit",
  "status": "pending",
  "ledger_account_id": "00001aaa-0000-0000-0000-000000000000",
  "ledger_account_lock_version": 194,
  "ledger_account_currency": "ledger_account_currency6",
  "ledger_account_currency_exponent": 164,
  "ledger_transaction_id": "ledger_transaction_id4",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "resulting_ledger_account_balances": {
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



# Ledger Account Statement

## Structure

`LedgerAccountStatement`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `ledger_id` | `uuid\|str` | Required | The id of the ledger that this ledger account statement belongs to. |
| `description` | `str` | Required | The description of the ledger account statement. |
| `ledger_account_id` | `uuid\|str` | Required | The id of the ledger account whose ledger entries are queried against, and its balances are computed as a result. |
| `ledger_account_lock_version` | `int` | Required | Lock version of the ledger account at the time of statement generation. |
| `ledger_account_normal_balance` | [`LedgerAccountNormalBalanceEnum`](../../doc/models/ledger-account-normal-balance-enum.md) | Required | The normal balance of the ledger account. |
| `effective_at_lower_bound` | `datetime` | Required | The inclusive lower bound of the effective_at timestamp of the ledger entries to be included in the ledger account statement. |
| `effective_at_upper_bound` | `datetime` | Required | The exclusive upper bound of the effective_at timestamp of the ledger entries to be included in the ledger account statement. |
| `starting_balance` | [`LedgerBalances`](../../doc/models/ledger-balances.md) | Required | - |
| `ending_balance` | [`LedgerBalances`](../../doc/models/ledger-balances.md) | Required | - |
| `metadata` | `Dict[str, str]` | Required | Additional data represented as key-value pairs. Both the key and value must be strings. |

## Example (as JSON)

```json
{
  "id": "0000023a-0000-0000-0000-000000000000",
  "object": "object8",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "ledger_id": "00000248-0000-0000-0000-000000000000",
  "description": "description0",
  "ledger_account_id": "000016c0-0000-0000-0000-000000000000",
  "ledger_account_lock_version": 180,
  "ledger_account_normal_balance": "credit",
  "effective_at_lower_bound": "2016-03-13T12:52:32.123Z",
  "effective_at_upper_bound": "2016-03-13T12:52:32.123Z",
  "starting_balance": {
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
  },
  "ending_balance": {
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
  },
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  }
}
```



# Ledger Balances with Effective At

## Structure

`LedgerBalancesWithEffectiveAt`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `effective_at_lower_bound` | `datetime` | Required | The inclusive lower bound of the effective_at timestamp for the returned balances. |
| `effective_at_upper_bound` | `datetime` | Required | The exclusive upper bound of the effective_at timestamp for the returned balances. |
| `pending_balance` | [`LedgerBalance`](../../doc/models/ledger-balance.md) | Required | - |
| `posted_balance` | [`LedgerBalance`](../../doc/models/ledger-balance.md) | Required | - |
| `available_balance` | [`LedgerBalance`](../../doc/models/ledger-balance.md) | Required | - |

## Example (as JSON)

```json
{
  "effective_at_lower_bound": "2016-03-13T12:52:32.123Z",
  "effective_at_upper_bound": "2016-03-13T12:52:32.123Z",
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
```


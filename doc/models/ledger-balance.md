
# Ledger Balance

## Structure

`LedgerBalance`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `credits` | `int` | Required | - |
| `debits` | `int` | Required | - |
| `amount` | `int` | Required | - |
| `currency` | `str` | Required | The currency of the ledger account. |
| `currency_exponent` | `int` | Required | The currency exponent of the ledger account. |

## Example (as JSON)

```json
{
  "credits": 186,
  "debits": 106,
  "amount": 244,
  "currency": "currency2",
  "currency_exponent": 190
}
```


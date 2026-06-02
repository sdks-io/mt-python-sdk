
# Incoming Payment Detail Create Request

## Structure

`IncomingPaymentDetailCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | [`Type10Enum`](../../doc/models/type-10-enum.md) | Optional | One of `ach`, `wire`, `check`. |
| `direction` | [`Direction14Enum`](../../doc/models/direction-14-enum.md) | Optional | One of `credit`, `debit`. |
| `amount` | `int` | Optional | Value in specified currency's smallest unit. e.g. $10 would be represented as 1000. |
| `currency` | [`CurrencyEnum`](../../doc/models/currency-enum.md) | Optional | Three-letter ISO currency code. |
| `internal_account_id` | `uuid\|str` | Optional | The ID of one of your internal accounts. |
| `virtual_account_id` | `uuid\|str` | Optional | An optional parameter to associate the incoming payment detail to a virtual account. |
| `as_of_date` | `date` | Optional | Defaults to today. |
| `description` | `str` | Optional | Defaults to a random description. |

## Example (as JSON)

```json
{
  "type": "interac",
  "direction": "credit",
  "amount": 116,
  "currency": "GIP",
  "internal_account_id": "00001d14-0000-0000-0000-000000000000"
}
```


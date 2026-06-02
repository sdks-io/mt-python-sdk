
# Account Detail Create Request

## Structure

`AccountDetailCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_number` | `str` | Required | The account number for the bank account. |
| `account_number_type` | [`AccountNumberTypeEnum`](../../doc/models/account-number-type-enum.md) | Optional | One of `iban`, `clabe`, `wallet_address`, or `other`. Use `other` if the bank account number is in a generic format. |

## Example (as JSON)

```json
{
  "account_number": "account_number0",
  "account_number_type": "iban"
}
```


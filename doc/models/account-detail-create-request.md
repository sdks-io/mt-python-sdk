
# Account Detail Create Request

*This model accepts additional fields of type Any.*

## Structure

`AccountDetailCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account_number` | `str` | Required | The account number for the bank account. |
| `account_number_type` | [`AccountNumberType`](../../doc/models/account-number-type.md) | Optional | One of `iban`, `clabe`, `wallet_address`, or `other`. Use `other` if the bank account number is in a generic format. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "account_number": "account_number0",
  "account_number_type": "iban",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


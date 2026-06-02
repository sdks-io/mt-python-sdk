
# Ledger Account Category Create Request

*This model accepts additional fields of type Any.*

## Structure

`LedgerAccountCategoryCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Required | The name of the ledger account category. |
| `description` | `str` | Optional | The description of the ledger account category. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `currency` | `str` | Required | The currency of the ledger account category. |
| `currency_exponent` | `int` | Optional | The currency exponent of the ledger account category. |
| `ledger_id` | `uuid\|str` | Required | The id of the ledger that this account category belongs to. |
| `normal_balance` | [`NormalBalance2`](../../doc/models/normal-balance-2.md) | Required | The normal balance of the ledger account category. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "name": "name2",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "currency": "currency2",
  "ledger_id": "000005ce-0000-0000-0000-000000000000",
  "normal_balance": "credit",
  "description": "description2",
  "currency_exponent": 80,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


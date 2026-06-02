
# Ledger Account Create Request

*This model accepts additional fields of type Any.*

## Structure

`LedgerAccountCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Required | The name of the ledger account. |
| `description` | `str` | Optional | The description of the ledger account. |
| `normal_balance` | [`NormalBalance`](../../doc/models/normal-balance.md) | Required | The normal balance of the ledger account. |
| `ledger_id` | `uuid\|str` | Required | The id of the ledger that this account belongs to. |
| `currency` | `str` | Required | The currency of the ledger account. |
| `currency_exponent` | `int` | Optional | The currency exponent of the ledger account. |
| `ledgerable_id` | `uuid\|str` | Optional | If the ledger account links to another object in Modern Treasury, the id will be populated here, otherwise null. |
| `ledgerable_type` | [`LedgerableType`](../../doc/models/ledgerable-type.md) | Optional | If the ledger account links to another object in Modern Treasury, the type will be populated here, otherwise null. The value is one of internal_account or external_account. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "name": "name2",
  "normal_balance": "credit",
  "ledger_id": "00000100-0000-0000-0000-000000000000",
  "currency": "currency2",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "description": "description2",
  "currency_exponent": 30,
  "ledgerable_id": "000022fa-0000-0000-0000-000000000000",
  "ledgerable_type": "external_account",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


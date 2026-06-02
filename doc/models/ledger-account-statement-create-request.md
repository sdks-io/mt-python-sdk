
# Ledger Account Statement Create Request

*This model accepts additional fields of type Any.*

## Structure

`LedgerAccountStatementCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `description` | `str` | Optional | The description of the ledger account statement. |
| `ledger_account_id` | `uuid\|str` | Required | The id of the ledger account whose ledger entries are queried against, and its balances are computed as a result. |
| `effective_at_lower_bound` | `datetime` | Required | The inclusive lower bound of the effective_at timestamp of the ledger entries to be included in the ledger account statement. |
| `effective_at_upper_bound` | `datetime` | Required | The exclusive upper bound of the effective_at timestamp of the ledger entries to be included in the ledger account statement. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ledger_account_id": "00001e5a-0000-0000-0000-000000000000",
  "effective_at_lower_bound": "2016-03-13T12:52:32.123Z",
  "effective_at_upper_bound": "2016-03-13T12:52:32.123Z",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "description": "description6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


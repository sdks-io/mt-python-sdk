
# Ledger Event Handler

## Structure

`LedgerEventHandler`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `discarded_at` | `datetime` | Required | - |
| `name` | `str` | Required | Name of the ledger event handler. |
| `description` | `str` | Required | An optional description. |
| `ledger_transaction_template` | [`LedgerEventHandlerLedgerTransactionTemplate`](../../doc/models/ledger-event-handler-ledger-transaction-template.md) | Required | - |
| `conditions` | [`LedgerEventHandlerConditions`](../../doc/models/ledger-event-handler-conditions.md) | Required | - |
| `metadata` | `Dict[str, str]` | Required | Additional data represented as key-value pairs. Both the key and value must be strings. |

## Example (as JSON)

```json
{
  "id": "000001aa-0000-0000-0000-000000000000",
  "object": "object4",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "discarded_at": "2016-03-13T12:52:32.123Z",
  "name": "name6",
  "description": "description6",
  "ledger_transaction_template": {
    "description": "description4",
    "effective_at": "effective_at2",
    "ledger_entries": [
      {
        "amount": "amount6",
        "direction": "direction0",
        "ledger_account_id": "ledger_account_id8"
      }
    ],
    "metadata": {
      "key": "value",
      "foo": "bar",
      "modern": "treasury"
    }
  },
  "conditions": {
    "field": "field6",
    "operator": "operator8",
    "value": "value4"
  },
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  }
}
```


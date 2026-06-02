
# Ledger Account Payout

## Structure

`LedgerAccountPayout`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `ledger_id` | `uuid\|str` | Required | The id of the ledger that this ledger account payout belongs to. |
| `description` | `str` | Required | The description of the ledger account payout. |
| `status` | [`Status6Enum`](../../doc/models/status-6-enum.md) | Required | The status of the ledger account payout. One of `processing`, `pending`, `posted`, `archiving` or `archived`. |
| `payout_ledger_account_id` | `uuid\|str` | Required | The id of the payout ledger account whose ledger entries are queried against, and its balance is reduced as a result. |
| `funding_ledger_account_id` | `uuid\|str` | Required | The id of the funding ledger account that sends to or receives funds from the payout ledger account. |
| `effective_at_upper_bound` | `datetime` | Required | The exclusive upper bound of the effective_at timestamp of the ledger entries to be included in the ledger account payout. The default value is the created_at timestamp of the ledger account payout. |
| `ledger_transaction_id` | `uuid\|str` | Required | The id of the ledger transaction that this payout is associated with. |
| `amount` | `int` | Required | The amount of the ledger account payout. |
| `currency` | `str` | Required | The currency of the ledger account payout. |
| `currency_exponent` | `int` | Required | The currency exponent of the ledger account payout. |
| `metadata` | `Dict[str, str]` | Required | Additional data represented as key-value pairs. Both the key and value must be strings. |

## Example (as JSON)

```json
{
  "id": "00001d3e-0000-0000-0000-000000000000",
  "object": "object6",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "ledger_id": "00001d4c-0000-0000-0000-000000000000",
  "description": "description4",
  "status": "pending",
  "payout_ledger_account_id": "000008b6-0000-0000-0000-000000000000",
  "funding_ledger_account_id": "0000217e-0000-0000-0000-000000000000",
  "effective_at_upper_bound": "2016-03-13T12:52:32.123Z",
  "ledger_transaction_id": "000024a4-0000-0000-0000-000000000000",
  "amount": 176,
  "currency": "currency6",
  "currency_exponent": 2,
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  }
}
```


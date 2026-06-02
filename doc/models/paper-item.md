
# Paper Item

## Structure

`PaperItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `transaction_line_item_id` | `uuid\|str` | Required | The ID of the reconciled Transaction Line Item or `null`. |
| `transaction_id` | `uuid\|str` | Required | The ID of the reconciled Transaction or `null`. |
| `status` | [`Status16`](../../doc/models/status-16.md) | Required | The current status of the paper item. One of `pending`, `completed`, or `returned`. |
| `lockbox_number` | `str` | Required | The identifier for the lockbox assigned by the bank. |
| `deposit_date` | `date` | Required | The date the paper item was deposited into your organization's bank account. |
| `amount` | `int` | Required | The amount of the paper item. |
| `currency` | [`Currency`](../../doc/models/currency.md) | Required | Three-letter ISO currency code. |
| `account_number` | `str` | Required | The account number on the paper item. |
| `account_number_safe` | `str` | Required | The last 4 digits of the account_number. |
| `routing_number` | `str` | Required | The routing number on the paper item. |
| `check_number` | `str` | Required | The check number on the paper item. |
| `remitter_name` | `str` | Required | The name of the remitter on the paper item. |
| `memo_field` | `str` | Required | The memo field on the paper item. |

## Example (as JSON)

```json
{
  "id": "000022cc-0000-0000-0000-000000000000",
  "object": "object4",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "transaction_line_item_id": "00001e5c-0000-0000-0000-000000000000",
  "transaction_id": "0000261c-0000-0000-0000-000000000000",
  "status": "returned",
  "lockbox_number": "lockbox_number8",
  "deposit_date": "2016-03-13",
  "amount": 78,
  "currency": "BYR",
  "account_number": "account_number2",
  "account_number_safe": "account_number_safe2",
  "routing_number": "routing_number2",
  "check_number": "check_number0",
  "remitter_name": "remitter_name4",
  "memo_field": "memo_field8"
}
```


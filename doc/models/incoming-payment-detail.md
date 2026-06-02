
# Incoming Payment Detail

## Structure

`IncomingPaymentDetail`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `internal_account_id` | `uuid\|str` | Required | The ID of the Internal Account for the incoming payment detail. This is always present. |
| `virtual_account_id` | `uuid\|str` | Required | If the incoming payment detail is in a virtual account, the ID of the Virtual Account. |
| `virtual_account` | [`VirtualAccount`](../../doc/models/virtual-account.md) | Required | - |
| `transaction_line_item_id` | `uuid\|str` | Required | The ID of the reconciled Transaction Line Item or `null`. |
| `transaction_id` | `uuid\|str` | Required | The ID of the reconciled Transaction or `null`. |
| `ledger_transaction_id` | `uuid\|str` | Required | The ID of the ledger transaction linked to the incoming payment detail or `null`. |
| `mtype` | [`Type4`](../../doc/models/type-4.md) | Required | One of: `ach`, `book`, `check`, `eft`, `interac`, `rtp`, `sepa`, `signet`, or `wire`. |
| `data` | `Any` | Required | The raw data from the payment pre-notification file that we get from the bank. |
| `amount` | `int` | Required | Value in specified currency's smallest unit. e.g. $10 would be represented as 1000. |
| `currency` | [`Currency`](../../doc/models/currency.md) | Required | Three-letter ISO currency code. |
| `direction` | [`Direction4`](../../doc/models/direction-4.md) | Required | One of `credit` or `debit`. |
| `status` | [`Status2`](../../doc/models/status-2.md) | Required | The current status of the incoming payment order. One of `pending`, `completed`, or `returned`. |
| `metadata` | `Dict[str, str]` | Required | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `as_of_date` | `date` | Required | The date on which the corresponding transaction will occur. |
| `vendor_id` | `uuid\|str` | Required | The identifier of the vendor bank. |
| `originating_routing_number` | `str` | Required | The routing number of the originating account for the incoming payment detail. |
| `originating_routing_number_type` | [`OriginatingRoutingNumberType`](../../doc/models/originating-routing-number-type.md) | Required | The type of the originating routing number for the incoming payment detail. |
| `originating_account_number` | `str` | Optional | The account number of the originating account for the incoming payment detail. |
| `originating_account_number_safe` | `str` | Required | The last 4 digits of the originating account_number for the incoming payment detail. |
| `originating_account_number_type` | [`OriginatingAccountNumberType`](../../doc/models/originating-account-number-type.md) | Required | The type of the originating account number for the incoming payment detail. |

## Example (as JSON)

```json
{
  "id": "0000265e-0000-0000-0000-000000000000",
  "object": "object0",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "internal_account_id": "00001280-0000-0000-0000-000000000000",
  "virtual_account_id": "0000012a-0000-0000-0000-000000000000",
  "virtual_account": {
    "id": "0000016a-0000-0000-0000-000000000000",
    "object": "object0",
    "live_mode": false,
    "created_at": "2016-03-13T12:52:32.123Z",
    "updated_at": "2016-03-13T12:52:32.123Z",
    "discarded_at": "2016-03-13T12:52:32.123Z",
    "name": "name2",
    "description": "description2",
    "counterparty_id": "0000071e-0000-0000-0000-000000000000",
    "internal_account_id": "0000149c-0000-0000-0000-000000000000",
    "account_details": [
      {
        "id": "00000bf8-0000-0000-0000-000000000000",
        "object": "object8",
        "live_mode": false,
        "created_at": "2016-03-13T12:52:32.123Z",
        "updated_at": "2016-03-13T12:52:32.123Z",
        "discarded_at": "2016-03-13T12:52:32.123Z",
        "account_number": "account_number6",
        "account_number_type": "other",
        "account_number_safe": "account_number_safe6"
      }
    ],
    "routing_details": [
      {
        "id": "00001b96-0000-0000-0000-000000000000",
        "object": "object0",
        "live_mode": false,
        "created_at": "2016-03-13T12:52:32.123Z",
        "updated_at": "2016-03-13T12:52:32.123Z",
        "discarded_at": "2016-03-13T12:52:32.123Z",
        "routing_number": "routing_number6",
        "routing_number_type": "gb_sort_code",
        "payment_type": "eft",
        "bank_name": "bank_name2",
        "bank_address": {
          "id": "000004a8-0000-0000-0000-000000000000",
          "object": "object0",
          "live_mode": false,
          "created_at": "2016-03-13T12:52:32.123Z",
          "updated_at": "2016-03-13T12:52:32.123Z",
          "line1": "line14",
          "line2": "line26",
          "locality": "locality2",
          "region": "region8",
          "postal_code": "postal_code4",
          "country": "country6"
        }
      }
    ],
    "debit_ledger_account_id": "000001e2-0000-0000-0000-000000000000",
    "credit_ledger_account_id": "00001962-0000-0000-0000-000000000000",
    "metadata": {
      "key": "value",
      "foo": "bar",
      "modern": "treasury"
    }
  },
  "transaction_line_item_id": "000021ee-0000-0000-0000-000000000000",
  "transaction_id": "0000029e-0000-0000-0000-000000000000",
  "ledger_transaction_id": "00000b8c-0000-0000-0000-000000000000",
  "type": "book",
  "data": {
    "key1": "val1",
    "key2": "val2"
  },
  "amount": 32,
  "currency": "NZD",
  "direction": "credit",
  "status": "pending",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "as_of_date": "2016-03-13",
  "vendor_id": "00000e5a-0000-0000-0000-000000000000",
  "originating_routing_number": "originating_routing_number4",
  "originating_routing_number_type": "chips",
  "originating_account_number_safe": "originating_account_number_safe4",
  "originating_account_number_type": "clabe",
  "originating_account_number": "originating_account_number8"
}
```


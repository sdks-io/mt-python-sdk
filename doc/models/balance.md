
# Balance

## Structure

`Balance`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `amount` | `int` | Required | The balance amount. |
| `currency` | [`Currency`](../../doc/models/currency.md) | Required | Three-letter ISO currency code. |
| `balance_type` | [`BalanceType`](../../doc/models/balance-type.md) | Required | The specific type of balance reported. One of `opening_ledger`, `closing_ledger`, `current_ledger`, `opening_available`, `opening_available_next_business_day`, `closing_available`, `current_available`, or `other`. |
| `vendor_code` | `str` | Required | The code used by the bank when reporting this specific balance. |
| `vendor_code_type` | [`VendorCodeType`](../../doc/models/vendor-code-type.md) | Required | The code used by the bank when reporting this specific balance. |

## Example (as JSON)

```json
{
  "id": "00002660-0000-0000-0000-000000000000",
  "object": "object2",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "amount": 18,
  "currency": "SGD",
  "balance_type": "closing_available",
  "vendor_code": "vendor_code6",
  "vendor_code_type": "currencycloud"
}
```


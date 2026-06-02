
# Connection

## Structure

`Connection`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `discarded_at` | `datetime` | Required | - |
| `vendor_id` | `uuid\|str` | Required | Unique identifier for the bank or vendor. |
| `vendor_customer_id` | `uuid\|str` | Required | An identifier given to this connection by the bank. |
| `vendor_name` | `str` | Required | A human-friendly name for the bank or vendor. |

## Example (as JSON)

```json
{
  "id": "00001eee-0000-0000-0000-000000000000",
  "object": "object4",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "discarded_at": "2016-03-13T12:52:32.123Z",
  "vendor_id": "00002026-0000-0000-0000-000000000000",
  "vendor_customer_id": "0000080c-0000-0000-0000-000000000000",
  "vendor_name": "vendor_name0"
}
```


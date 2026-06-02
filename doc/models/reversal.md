
# Reversal

## Structure

`Reversal`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `status` | [`Status19`](../../doc/models/status-19.md) | Required | The current status of the reversal. |
| `payment_order_id` | `uuid\|str` | Required | The ID of the relevant Payment Order. |
| `metadata` | `Dict[str, str]` | Required | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `reason` | [`Reason`](../../doc/models/reason.md) | Required | The reason for the reversal. |

## Example (as JSON)

```json
{
  "id": "00001e40-0000-0000-0000-000000000000",
  "object": "object2",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "status": "pending",
  "payment_order_id": "00001674-0000-0000-0000-000000000000",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "reason": "duplicate"
}
```


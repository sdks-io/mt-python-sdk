
# Contact Detail

## Structure

`ContactDetail`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `discarded_at` | `datetime` | Required | - |
| `contact_identifier` | `str` | Required | - |
| `contact_identifier_type` | [`ContactIdentifierType`](../../doc/models/contact-identifier-type.md) | Required | - |

## Example (as JSON)

```json
{
  "id": "00001c0c-0000-0000-0000-000000000000",
  "object": "object2",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "discarded_at": "2016-03-13T12:52:32.123Z",
  "contact_identifier": "contact_identifier2",
  "contact_identifier_type": "website"
}
```


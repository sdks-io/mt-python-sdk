
# Ledger

*This model accepts additional fields of type Any.*

## Structure

`Ledger`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Required | - |
| `object` | `str` | Required | - |
| `live_mode` | `bool` | Required | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Required | - |
| `updated_at` | `datetime` | Required | - |
| `discarded_at` | `datetime` | Required | - |
| `name` | `str` | Required | The name of the ledger. |
| `description` | `str` | Required | An optional free-form description for internal use. |
| `metadata` | `Dict[str, str]` | Required | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "id": "00000218-0000-0000-0000-000000000000",
  "object": "object4",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "discarded_at": "2016-03-13T12:52:32.123Z",
  "name": "name6",
  "description": "description6",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


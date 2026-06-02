
# Contact Detail Create Request

*This model accepts additional fields of type Any.*

## Structure

`ContactDetailCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contact_identifier` | `str` | Optional | - |
| `contact_identifier_type` | [`ContactIdentifierType`](../../doc/models/contact-identifier-type.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "contact_identifier": "contact_identifier0",
  "contact_identifier_type": "email",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


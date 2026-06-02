
# Document Create Request

*This model accepts additional fields of type Any.*

## Structure

`DocumentCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documentable_id` | `str` | Required | The unique identifier for the associated object. |
| `documentable_type` | [`DocumentableType1`](../../doc/models/documentable-type-1.md) | Required | - |
| `document_type` | `str` | Optional | A category given to the document, can be `null`. |
| `file` | `binary` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "documentable_id": "documentable_id4",
  "documentable_type": "connections",
  "document_type": "document_type4",
  "file": "data:text/plain;name=dummy_file;base64,",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


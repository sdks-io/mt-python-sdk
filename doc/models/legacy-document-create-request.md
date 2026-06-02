
# Legacy Document Create Request

*This model accepts additional fields of type Any.*

## Structure

`LegacyDocumentCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `document_type` | `str` | Optional | A category given to the document, can be `null`. |
| `file` | `binary` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "document_type": "document_type0",
  "file": "data:text/plain;name=dummy_file;base64,",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


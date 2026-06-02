
# Legacy Document Create Request

## Structure

`LegacyDocumentCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `document_type` | `str` | Optional | A category given to the document, can be `null`. |
| `file` | `binary` | Required | - |

## Example (as JSON)

```json
{
  "document_type": "document_type0",
  "file": "data:text/plain;name=dummy_file;base64,"
}
```


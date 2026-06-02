
# Document Create Request

## Structure

`DocumentCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documentable_id` | `str` | Required | The unique identifier for the associated object. |
| `documentable_type` | [`DocumentableType1Enum`](../../doc/models/documentable-type-1-enum.md) | Required | - |
| `document_type` | `str` | Optional | A category given to the document, can be `null`. |
| `file` | `binary` | Required | - |

## Example (as JSON)

```json
{
  "documentable_id": "documentable_id4",
  "documentable_type": "connections",
  "document_type": "document_type4",
  "file": "data:text/plain;name=dummy_file;base64,"
}
```


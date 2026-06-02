
# Internal Account Update Request

*This model accepts additional fields of type Any.*

## Structure

`InternalAccountUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Optional | The nickname for the internal account. |
| `metadata` | `Dict[str, str]` | Optional | Additional data in the form of key-value pairs. Pairs can be removed by passing an empty string or `null` as the value. |
| `parent_account_id` | `str` | Optional | The parent internal account for this account. |
| `counterparty_id` | `str` | Optional | The Counterparty associated to this account. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "name": "name6",
  "metadata": {
    "key0": "metadata3",
    "key1": "metadata2",
    "key2": "metadata1"
  },
  "parent_account_id": "parent_account_id4",
  "counterparty_id": "counterparty_id2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


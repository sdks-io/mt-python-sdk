
# Line Item Request

*This model accepts additional fields of type Any.*

## Structure

`LineItemRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount` | `int` | Required | Value in specified currency's smallest unit. e.g. $10 would be represented as 1000. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `description` | `str` | Optional | A free-form description of the line item. |
| `accounting_category_id` | `str` | Optional | The ID of one of your accounting categories. Note that these will only be accessible if your accounting system has been connected. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "amount": 92,
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "description": "description8",
  "accounting_category_id": "accounting_category_id8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# Invoice Line Item Create Request

*This model accepts additional fields of type Any.*

## Structure

`InvoiceLineItemCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Required | The name of the line item, typically a product or SKU name. |
| `description` | `str` | Optional | An optional free-form description of the line item. |
| `quantity` | `int` | Optional | The number of units of a product or service that this line item is for.           Must be a whole number. Defaults to 1 if not provided. |
| `unit_amount` | `int` | Required | The cost per unit of the product or service that this line item is for,           specified in the invoice currency's smallest unit. |
| `direction` | `str` | Optional | Either `debit` or `credit`. `debit` indicates that a client owes the business money           and increases the invoice's `total_amount` due. `credit` has the opposite intention and effect. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "name": "name2",
  "description": "description2",
  "quantity": 122,
  "unit_amount": 0,
  "direction": "direction8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


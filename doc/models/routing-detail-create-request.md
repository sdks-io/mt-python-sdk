
# Routing Detail Create Request

*This model accepts additional fields of type Any.*

## Structure

`RoutingDetailCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `routing_number` | `str` | Required | The routing number of the bank. |
| `routing_number_type` | [`RoutingNumberType`](../../doc/models/routing-number-type.md) | Required | One of `aba`, `swift`, `ca_cpa`, `au_bsb`, `gb_sort_code`, `in_ifsc`, `cnaps`. |
| `payment_type` | [`PaymentType1`](../../doc/models/payment-type-1.md) | Optional | If the routing detail is to be used for a specific payment type this field will be populated, otherwise null. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "routing_number": "routing_number0",
  "routing_number_type": "my_branch_code",
  "payment_type": "interac",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


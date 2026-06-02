
# Routing Detail 1

*This model accepts additional fields of type Any.*

## Structure

`RoutingDetail1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `routing_number` | `str` | Required | - |
| `routing_number_type` | [`RoutingNumberType1`](../../doc/models/routing-number-type-1.md) | Required | - |
| `payment_type` | [`PaymentType2`](../../doc/models/payment-type-2.md) | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "routing_number": "routing_number4",
  "routing_number_type": "br_codigo",
  "payment_type": "card",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


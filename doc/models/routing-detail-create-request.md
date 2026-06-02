
# Routing Detail Create Request

## Structure

`RoutingDetailCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `routing_number` | `str` | Required | The routing number of the bank. |
| `routing_number_type` | [`RoutingNumberTypeEnum`](../../doc/models/routing-number-type-enum.md) | Required | One of `aba`, `swift`, `ca_cpa`, `au_bsb`, `gb_sort_code`, `in_ifsc`, `cnaps`. |
| `payment_type` | [`PaymentType1Enum`](../../doc/models/payment-type-1-enum.md) | Optional | If the routing detail is to be used for a specific payment type this field will be populated, otherwise null. |

## Example (as JSON)

```json
{
  "routing_number": "routing_number0",
  "routing_number_type": "my_branch_code",
  "payment_type": "interac"
}
```


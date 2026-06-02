
# Counterparty Shipping Address

The counterparty's shipping address where physical goods should be delivered.

*This model accepts additional fields of type Any.*

## Structure

`CounterpartyShippingAddress`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `line_1` | `str` | Required | - |
| `line_2` | `str` | Optional | - |
| `locality` | `str` | Required | Locality or City. |
| `region` | `str` | Required | Region or State. |
| `postal_code` | `str` | Required | The postal code of the address. |
| `country` | `str` | Required | Country code conforms to [ISO 3166-1 alpha-2] |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "line1": "line14",
  "line2": "line26",
  "locality": "locality2",
  "region": "region8",
  "postal_code": "postal_code4",
  "country": "country6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# Party Address

The address associated with the owner or null.

*This model accepts additional fields of type Any.*

## Structure

`PartyAddress`

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
  "line1": "line12",
  "line2": "line24",
  "locality": "locality0",
  "region": "region6",
  "postal_code": "postal_code2",
  "country": "country4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


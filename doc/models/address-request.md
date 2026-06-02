
# Address Request

*This model accepts additional fields of type Any.*

## Structure

`AddressRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `line_1` | `str` | Optional | - |
| `line_2` | `str` | Optional | - |
| `locality` | `str` | Optional | Locality or City. |
| `region` | `str` | Optional | Region or State. |
| `postal_code` | `str` | Optional | The postal code of the address. |
| `country` | `str` | Optional | Country code conforms to [ISO 3166-1 alpha-2] |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "line1": "line10",
  "line2": "line22",
  "locality": "locality2",
  "region": "region4",
  "postal_code": "postal_code0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


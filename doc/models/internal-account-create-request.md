
# Internal Account Create Request

*This model accepts additional fields of type Any.*

## Structure

`InternalAccountCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `connection_id` | `str` | Required | The identifier of the financial institution the account belongs to. |
| `name` | `str` | Required | The nickname of the account. |
| `party_name` | `str` | Required | The legal name of the entity which owns the account. |
| `party_address` | [`PartyAddress`](../../doc/models/party-address.md) | Optional | The address associated with the owner or null. |
| `currency` | [`Currency1`](../../doc/models/currency-1.md) | Required | Either "USD" or "CAD". Internal accounts created at Increase only supports "USD". |
| `vendor_attributes` | `Dict[str, str]` | Optional | A hash of vendor specific attributes that will be used when creating the account at the vendor specified by the given connection. |
| `parent_account_id` | `str` | Optional | The parent internal account of this new account. |
| `counterparty_id` | `str` | Optional | The Counterparty associated to this account. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "connection_id": "connection_id8",
  "name": "name4",
  "party_name": "party_name6",
  "currency": "USD",
  "vendor_attributes": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "party_address": {
    "line1": "line18",
    "line2": "line20",
    "locality": "locality6",
    "region": "region2",
    "postal_code": "postal_code8",
    "country": "country0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "parent_account_id": "parent_account_id2",
  "counterparty_id": "counterparty_id0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# External Account Update Request

## Structure

`ExternalAccountUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `party_type` | [`PartyTypeEnum`](../../doc/models/party-type-enum.md) | Optional | Either `individual` or `business`. |
| `account_type` | [`AccountTypeEnum`](../../doc/models/account-type-enum.md) | Optional | Can be `checking`, `savings` or `other`. |
| `counterparty_id` | `uuid\|str` | Optional | - |
| `name` | `str` | Optional | A nickname for the external account. This is only for internal usage and won't affect any payments |
| `party_name` | `str` | Optional | If this value isn't provided, it will be inherited from the counterparty's name. |
| `party_address` | [`AddressRequest`](../../doc/models/address-request.md) | Optional | - |
| `metadata` | `Dict[str, str]` | Optional | Additional data in the form of key-value pairs. Pairs can be removed by passing an empty string or `null` as the value. |

## Example (as JSON)

```json
{
  "party_type": "business",
  "account_type": "cash",
  "counterparty_id": "0000137e-0000-0000-0000-000000000000",
  "name": "name4",
  "party_name": "party_name6"
}
```


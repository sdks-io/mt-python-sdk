
# Account

## Structure

`Account`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Optional | - |
| `object` | `str` | Optional | - |
| `live_mode` | `bool` | Optional | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Optional | - |
| `updated_at` | `datetime` | Optional | - |
| `discarded_at` | `datetime` | Optional | - |
| `account_type` | [`AccountTypeEnum`](../../doc/models/account-type-enum.md) | Optional | Can be `checking`, `savings` or `other`. |
| `party_type` | [`PartyTypeEnum`](../../doc/models/party-type-enum.md) | Optional | Either `individual` or `business`. |
| `party_address` | [`Address`](../../doc/models/address.md) | Optional | - |
| `name` | `str` | Optional | A nickname for the external account. This is only for internal usage and won't affect any payments |
| `account_details` | [`List[AccountDetail]`](../../doc/models/account-detail.md) | Optional | - |
| `routing_details` | [`List[RoutingDetail]`](../../doc/models/routing-detail.md) | Optional | - |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `party_name` | `str` | Optional | The legal name of the entity which owns the account. |
| `contact_details` | [`List[ContactDetail]`](../../doc/models/contact-detail.md) | Optional | - |
| `ledger_account_id` | `uuid\|str` | Optional | If the external account links to a ledger account in Modern Treasury, the id of the ledger account will be populated here. |
| `verification_status` | [`VerificationStatusEnum`](../../doc/models/verification-status-enum.md) | Optional | - |

## Example (as JSON)

```json
{
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "id": "00000120-0000-0000-0000-000000000000",
  "object": "object6",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z"
}
```


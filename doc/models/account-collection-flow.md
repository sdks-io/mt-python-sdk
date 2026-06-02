
# Account Collection Flow

## Structure

`AccountCollectionFlow`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Optional | - |
| `object` | `str` | Optional | - |
| `live_mode` | `bool` | Optional | This field will be true if this object exists in the live environment or false if it exists in the test environment. |
| `created_at` | `datetime` | Optional | - |
| `updated_at` | `datetime` | Optional | - |
| `client_token` | `str` | Optional | The client token of the account collection flow.  This token can be used to embed account collection in your client-side application. |
| `status` | [`StatusEnum`](../../doc/models/status-enum.md) | Optional | The current status of the account collection flow. One of `pending`, `completed`, `expired`, or `cancelled`. |
| `counterparty_id` | `uuid\|str` | Required | The ID of a counterparty. An external account created with this flow will be associated with this counterparty. |
| `external_account_id` | `uuid\|str` | Optional | If present, the ID of the external account created using this flow. |
| `payment_types` | [`List[PaymentTypeEnum]`](../../doc/models/payment-type-enum.md) | Required | - |

## Example (as JSON)

```json
{
  "id": "00000aa6-0000-0000-0000-000000000000",
  "object": "object4",
  "live_mode": false,
  "created_at": "2016-03-13T12:52:32.123Z",
  "updated_at": "2016-03-13T12:52:32.123Z",
  "counterparty_id": "0000021e-0000-0000-0000-000000000000",
  "payment_types": [
    "wire"
  ]
}
```


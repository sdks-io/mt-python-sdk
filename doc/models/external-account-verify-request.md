
# External Account Verify Request

*This model accepts additional fields of type Any.*

## Structure

`ExternalAccountVerifyRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `originating_account_id` | `uuid\|str` | Required | The ID of the internal account where the micro-deposits originate from. Both credit and debit capabilities must be enabled. |
| `payment_type` | [`PaymentType4`](../../doc/models/payment-type-4.md) | Required | Both ach and eft are supported payment types. |
| `currency` | [`Currency`](../../doc/models/currency.md) | Optional | Three-letter ISO currency code. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "originating_account_id": "00000bc6-0000-0000-0000-000000000000",
  "payment_type": "wire",
  "currency": "KWD",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


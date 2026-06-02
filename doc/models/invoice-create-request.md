
# Invoice Create Request

*This model accepts additional fields of type Any.*

## Structure

`InvoiceCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contact_details` | [`List[ContactDetail]`](../../doc/models/contact-detail.md) | Optional | The invoicer's contact details displayed at the top of the invoice. |
| `counterparty_id` | `str` | Required | The ID of the counterparty receiving the invoice. |
| `counterparty_billing_address` | [`CounterpartyBillingAddress`](../../doc/models/counterparty-billing-address.md) | Optional | The counterparty's billing address. |
| `counterparty_shipping_address` | [`CounterpartyShippingAddress`](../../doc/models/counterparty-shipping-address.md) | Optional | The counterparty's shipping address where physical goods should be delivered. |
| `currency` | [`Currency`](../../doc/models/currency.md) | Optional | Three-letter ISO currency code. |
| `description` | `str` | Optional | A free-form description of the invoice. |
| `due_date` | `datetime` | Required | A future date by when the invoice needs to be paid. |
| `invoicer_address` | [`InvoicerAddress`](../../doc/models/invoicer-address.md) | Optional | The invoice issuer's business address. |
| `originating_account_id` | `str` | Required | The ID of the internal account the invoice should be paid to. |
| `receiving_account_id` | `uuid\|str` | Optional | The receiving account ID. Can be an `external_account`. |
| `payment_effective_date` | `date` | Optional | Date transactions are to be posted to the participants' account. Defaults to the current business day or the next business day if the current day is a bank holiday or weekend. Format: yyyy-mm-dd. |
| `payment_type` | [`PaymentType6`](../../doc/models/payment-type-6.md) | Optional | One of `ach`, `eft`, `wire`, `check`, `sen`, `book`, `rtp`, `sepa`, `bacs`, `au_becs`, `interac`, `signet`, `provexchange`. |
| `payment_method` | [`PaymentMethod1`](../../doc/models/payment-method-1.md) | Optional | The method by which the invoice can be paid. `ui` will show the embedded payment collection flow. `automatic` will automatically initiate payment based upon the account details of the receiving_account id.\nIf the invoice amount is positive, the automatically initiated payment order's direction will be debit. If the invoice amount is negative, the automatically initiated payment order's direction will be credit. One of `manual`, `ui`, or `automatic`. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "contact_details": [
    {
      "id": "00002278-0000-0000-0000-000000000000",
      "object": "object2",
      "live_mode": false,
      "created_at": "2016-03-13T12:52:32.123Z",
      "updated_at": "2016-03-13T12:52:32.123Z",
      "discarded_at": "2016-03-13T12:52:32.123Z",
      "contact_identifier": "contact_identifier6",
      "contact_identifier_type": "phone_number"
    }
  ],
  "counterparty_id": "counterparty_id2",
  "counterparty_billing_address": {
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
  },
  "counterparty_shipping_address": {
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
  },
  "currency": "BMD",
  "description": "description2",
  "due_date": "2016-03-13T12:52:32.123Z",
  "originating_account_id": "originating_account_id8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# Expected Payment Update Request

*This model accepts additional fields of type Any.*

## Structure

`ExpectedPaymentUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount_upper_bound` | `int` | Optional | The highest amount this expected payment may be equal to. Value in specified currency's smallest unit. e.g. $10 would be represented as 1000. |
| `amount_lower_bound` | `int` | Optional | The lowest amount this expected payment may be equal to. Value in specified currency's smallest unit. e.g. $10 would be represented as 1000. |
| `direction` | [`Direction1`](../../doc/models/direction-1.md) | Optional | One of credit or debit. When you are receiving money, use credit. When you are being charged, use debit. |
| `internal_account_id` | `uuid\|str` | Optional | The ID of the Internal Account for the expected payment. |
| `mtype` | [`Type1`](../../doc/models/type-1.md) | Optional | One of: ach, au_becs, bacs, book, check, eft, interac, provxchange, rtp, sen, sepa, signet, wire. |
| `currency` | [`Currency`](../../doc/models/currency.md) | Optional | Three-letter ISO currency code. |
| `date_upper_bound` | `date` | Optional | The latest date the payment may come in. Format: yyyy-mm-dd |
| `date_lower_bound` | `date` | Optional | The earliest date the payment may come in. Format: yyyy-mm-dd |
| `description` | `str` | Optional | An optional description for internal use. |
| `statement_descriptor` | `str` | Optional | The statement description you expect to see on the transaction. For ACH payments, this will be the full line item passed from the bank. For wire payments, this will be the OBI field on the wire. For check payments, this will be the memo field. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `counterparty_id` | `uuid\|str` | Optional | The ID of the counterparty you expect for this payment. |
| `remittance_information` | `str` | Optional | For `ach`, this field will be passed through on an addenda record. For `wire` payments the field will be passed through as the "Originator to Beneficiary Information", also known as OBI or Fedwire tag 6000. |
| `reconciliation_groups` | `Any` | Optional | The reconciliation groups you have for this payment. |
| `reconciliation_filters` | `Any` | Optional | The reconciliation filters you have for this payment. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "amount_upper_bound": 152,
  "amount_lower_bound": 70,
  "direction": "credit",
  "internal_account_id": "00000db2-0000-0000-0000-000000000000",
  "type": "ach",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# Counterparty Update Request

## Structure

`CounterpartyUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Optional | A new name for the counterparty. Will only update if passed. |
| `email` | `str` | Optional | A new email for the counterparty. |
| `metadata` | `Dict[str, str]` | Optional | Additional data in the form of key-value pairs. Pairs can be removed by passing an empty string or `null` as the value. |
| `send_remittance_advice` | `bool` | Optional | If this is `true`, Modern Treasury will send an email to the counterparty whenever an associated payment order is sent to the bank. |
| `taxpayer_identifier` | `str` | Optional | Either a valid SSN or EIN. |

## Example (as JSON)

```json
{
  "name": "name8",
  "email": "email2",
  "metadata": {
    "key0": "metadata5",
    "key1": "metadata4",
    "key2": "metadata3"
  },
  "send_remittance_advice": false,
  "taxpayer_identifier": "taxpayer_identifier6"
}
```


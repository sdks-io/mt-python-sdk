
# Counterparty Create Request

## Structure

`CounterpartyCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Required | A human friendly name for this counterparty. |
| `accounts` | [`List[Account1]`](../../doc/models/account-1.md) | Optional | The accounts for this counterparty. |
| `email` | `str` | Optional | The counterparty's email. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `send_remittance_advice` | `bool` | Optional | Send an email to the counterparty whenever an associated payment order is sent to the bank. |
| `verification_status` | [`VerificationStatus1Enum`](../../doc/models/verification-status-1-enum.md) | Optional | The verification status of the counterparty. |
| `accounting` | [`Accounting1`](../../doc/models/accounting-1.md) | Optional | - |
| `ledger_type` | [`LedgerTypeEnum`](../../doc/models/ledger-type-enum.md) | Optional | An optional type to auto-sync the counterparty to your ledger. Either `customer` or `vendor`. |
| `taxpayer_identifier` | `str` | Optional | Either a valid SSN or EIN. |

## Example (as JSON)

```json
{
  "name": "name8",
  "metadata": {
    "key": "value",
    "foo": "bar",
    "modern": "treasury"
  },
  "accounts": [
    {
      "account_type": "other",
      "party_type": "business",
      "party_address": {
        "line1": "line18",
        "line2": "line20",
        "locality": "locality6",
        "region": "region2",
        "postal_code": "postal_code8"
      },
      "name": "name0",
      "account_details": [
        {
          "account_number": "account_number6",
          "account_number_type": "wallet_address"
        },
        {
          "account_number": "account_number6",
          "account_number_type": "wallet_address"
        },
        {
          "account_number": "account_number6",
          "account_number_type": "wallet_address"
        }
      ]
    },
    {
      "account_type": "other",
      "party_type": "business",
      "party_address": {
        "line1": "line18",
        "line2": "line20",
        "locality": "locality6",
        "region": "region2",
        "postal_code": "postal_code8"
      },
      "name": "name0",
      "account_details": [
        {
          "account_number": "account_number6",
          "account_number_type": "wallet_address"
        },
        {
          "account_number": "account_number6",
          "account_number_type": "wallet_address"
        },
        {
          "account_number": "account_number6",
          "account_number_type": "wallet_address"
        }
      ]
    }
  ],
  "email": "email8",
  "send_remittance_advice": false,
  "verification_status": "unverified"
}
```


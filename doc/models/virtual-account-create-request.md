
# Virtual Account Create Request

*This model accepts additional fields of type Any.*

## Structure

`VirtualAccountCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `str` | Required | The name of the virtual account. |
| `description` | `str` | Optional | An optional description for internal use. |
| `counterparty_id` | `uuid\|str` | Optional | The ID of the counterparty that the virtual account belongs to. |
| `internal_account_id` | `uuid\|str` | Required | The ID of the internal account that this virtual account is associated with. |
| `account_details` | [`List[AccountDetailCreateRequest]`](../../doc/models/account-detail-create-request.md) | Optional | An array of account detail objects. |
| `routing_details` | [`List[RoutingDetailCreateRequest]`](../../doc/models/routing-detail-create-request.md) | Optional | An array of routing detail objects. |
| `debit_ledger_account_id` | `uuid\|str` | Optional | The ID of a debit normal ledger account. When money enters the virtual account, this ledger account will be debited. Must be accompanied by a credit_ledger_account_id if present. |
| `credit_ledger_account_id` | `uuid\|str` | Optional | The ID of a credit normal ledger account. When money leaves the virtual account, this ledger account will be credited. Must be accompanied by a debit_ledger_account_id if present. |
| `metadata` | `Dict[str, str]` | Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "name": "name2",
  "description": "description2",
  "counterparty_id": "00001254-0000-0000-0000-000000000000",
  "internal_account_id": "00000966-0000-0000-0000-000000000000",
  "account_details": [
    {
      "account_number": "account_number6",
      "account_number_type": "other",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "account_number": "account_number6",
      "account_number_type": "other",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "routing_details": [
    {
      "routing_number": "routing_number6",
      "routing_number_type": "gb_sort_code",
      "payment_type": "eft",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "routing_number": "routing_number6",
      "routing_number_type": "gb_sort_code",
      "payment_type": "eft",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "debit_ledger_account_id": "00000d18-0000-0000-0000-000000000000",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


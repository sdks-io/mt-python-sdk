
# Return Create Request

*This model accepts additional fields of type Any.*

## Structure

`ReturnCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `returnable_id` | `uuid\|str` | Required | The ID of the object being returned or `null`. |
| `code` | [`Code1`](../../doc/models/code-1.md) | Optional | The return code. For ACH returns, this is the required ACH return code. |
| `reason` | `str` | Optional | An optional description of the reason for the return. This is for internal usage and will not be transmitted to the bank.” |
| `date_of_death` | `date` | Optional | If the return code is `R14` or `R15` this is the date the deceased counterparty passed away. |
| `additional_information` | `str` | Optional | Some returns may include additional information from the bank. In these cases, this string will be present. |
| `returnable_type` | `str` | Required, Constant | The type of object being returned. Currently, this may only be incoming_payment_detail.<br><br>**Value**: `"incoming_payment_detail"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "returnable_id": "00000936-0000-0000-0000-000000000000",
  "returnable_type": "incoming_payment_detail",
  "code": "R17",
  "reason": "reason8",
  "date_of_death": "2016-03-13",
  "additional_information": "additional_information6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


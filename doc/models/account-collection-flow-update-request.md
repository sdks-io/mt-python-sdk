
# Account Collection Flow Update Request

## Structure

`AccountCollectionFlowUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `str` | Required, Constant | Required. The updated status of the account collection flow. Can only be used to mark a flow as `cancelled`.<br><br>**Value**: `"cancelled"` |

## Example (as JSON)

```json
{
  "status": "cancelled"
}
```


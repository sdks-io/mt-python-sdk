# Validation

```python
validation_api = client.validation
```

## Class Name

`ValidationApi`


# Validate Routing Number

Validates the routing number information supplied without creating a routing detail

```python
def validate_routing_number(self,
                           routing_number,
                           routing_number_type)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `routing_number` | `str` | Query, Required | The routing number that is being validated. |
| `routing_number_type` | [`RoutingNumberType8`](../../doc/models/routing-number-type-8.md) | Query, Required | One of `aba`, `au_bsb`, `br_codigo`, `ca_cpa`, `cnaps`, `gb_sort_code`, `in_ifsc`, `my_branch_code`, or `swift`. In sandbox mode we currently only support `aba` and `swift` with routing numbers '123456789' and 'GRINUST0XXX' respectively. |

## Response Type

**200**: successful valid routing number and type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RoutingNumberLookupRequest`](../../doc/models/routing-number-lookup-request.md).

## Example Usage

```python
routing_number = 'routing_number4'

routing_number_type = RoutingNumberType8.MY_BRANCH_CODE

result = validation_api.validate_routing_number(
    routing_number,
    routing_number_type
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful with invalid parameter | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


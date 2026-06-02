# Ping

```python
ping_api = client.ping
```

## Class Name

`PingApi`


# Ping API

A test endpoint often used to confirm credentials and headers are being passed in correctly.

```python
def ping_api(self)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PingResponse`](../../doc/models/ping-response.md).

## Example Usage

```python
result = ping_api.ping_api()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 429 | unsuccessful | `ApiException` |
| 500 | internal server error | `ApiException` |


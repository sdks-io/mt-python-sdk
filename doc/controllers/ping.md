# Ping

```python
ping_controller = client.ping
```

## Class Name

`PingController`


# Ping API

A test endpoint often used to confirm credentials and headers are being passed in correctly.

```python
def ping_api(self)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Response Type

**200**: successful

[`PingResponse`](../../doc/models/ping-response.md)

## Example Usage

```python
result = ping_controller.ping_api()
print(result)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 429 | unsuccessful | `APIException` |
| 500 | internal server error | `APIException` |


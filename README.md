
# Getting Started with Modern Treasury

## Introduction

The Modern Treasury REST API. Please see https://docs.moderntreasury.com for more details.

## Install the Package

The package is compatible with Python versions `3.7+`.
Install the package from PyPi using the following pip command:

```bash
pip install mt-sdk==0.0.4
```

You can also view the package at:
https://pypi.python.org/pypi/mt-sdk/0.0.4

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| http_client_instance | `Union[Session, HttpClientProvider]` | The Http Client passed from the sdk user for making requests |
| override_http_client_configuration | `bool` | The value which determines to override properties of the passed Http Client from the sdk user |
| http_call_back | `HttpCallBack` | The callback value that is invoked before and after an HTTP call is made to an endpoint |
| timeout | `float` | The value to use for connection timeout. <br> **Default: 30** |
| max_retries | `int` | The number of times to retry an endpoint call if it fails. <br> **Default: 0** |
| backoff_factor | `float` | A backoff factor to apply between attempts after the second try. <br> **Default: 2** |
| retry_statuses | `Array of int` | The http statuses on which retry is to be done. <br> **Default: [408, 413, 429, 500, 502, 503, 504, 521, 522, 524]** |
| retry_methods | `Array of string` | The http methods on which retry is to be done. <br> **Default: ["GET", "PUT"]** |
| proxy_settings | [`ProxySettings`](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/proxy-settings.md) | Optional proxy configuration to route HTTP requests through a proxy server. |
| logging_configuration | [`LoggingConfiguration`](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/logging-configuration.md) | The SDK logging configuration for API calls |
| basic_auth_credentials | [`BasicAuthCredentials`](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/auth/basic-authentication.md) | The credential object for Basic Authentication |

The API client can be initialized as follows:

### Code-Based Client Initialization

```python
import logging

from moderntreasury.configuration import Environment
from moderntreasury.http.auth.basic_auth import BasicAuthCredentials
from moderntreasury.logging.configuration.api_logging_configuration import LoggingConfiguration
from moderntreasury.logging.configuration.api_logging_configuration import RequestLoggingConfiguration
from moderntreasury.logging.configuration.api_logging_configuration import ResponseLoggingConfiguration
from moderntreasury.moderntreasury_client import ModerntreasuryClient

client = ModerntreasuryClient(
    basic_auth_credentials=BasicAuthCredentials(
        username='BasicAuthUserName',
        password='BasicAuthPassword'
    ),
    environment=Environment.PRODUCTION,
    logging_configuration=LoggingConfiguration(
        log_level=logging.INFO,
        request_logging_config=RequestLoggingConfiguration(
            log_body=True
        ),
        response_logging_config=ResponseLoggingConfiguration(
            log_headers=True
        )
    )
)
```

### Environment-Based Client Initialization

```python
from moderntreasury.moderntreasury_client import ModerntreasuryClient

# Specify the path to your .env file if it’s located outside the project’s root directory.
client = ModerntreasuryClient.from_environment(dotenv_path='/path/to/.env')
```

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/environment-based-client-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| PRODUCTION | **Default** |
| ENVIRONMENT2 | - |

## Authorization

This API uses the following authentication schemes.

* [`basic_auth (Basic Authentication)`](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/auth/basic-authentication.md)

## List of APIs

* [Account Detail](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/account-detail.md)
* [Balance Report](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/balance-report.md)
* [Connection](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/connection.md)
* [Counterparty](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/counterparty.md)
* [Document](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/document.md)
* [Event](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/event.md)
* [Expected Payment](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/expected-payment.md)
* [External Account](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/external-account.md)
* [Incoming Payment Detail](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/incoming-payment-detail.md)
* [Internal Account](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/internal-account.md)
* [Invoice Line Item](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/invoice-line-item.md)
* [Invoice](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/invoice.md)
* [Ledger Account Category](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledger-account-category.md)
* [Ledger Account Payout](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledger-account-payout.md)
* [Ledger Account Statement](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledger-account-statement.md)
* [Ledger Account](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledger-account.md)
* [Ledger Entry](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledger-entry.md)
* [Ledger Event Handler](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledger-event-handler.md)
* [Ledger Transaction](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledger-transaction.md)
* [Ledgerable Event](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledgerable-event.md)
* [Ledger](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ledger.md)
* [Line Item](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/line-item.md)
* [Paper Item](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/paper-item.md)
* [Payment Order](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/payment-order.md)
* [Payment Reference](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/payment-reference.md)
* [Ping](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/ping.md)
* [Return](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/return.md)
* [Reversal](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/reversal.md)
* [Routing Detail](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/routing-detail.md)
* [Transaction Line Item](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/transaction-line-item.md)
* [Transaction](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/transaction.md)
* [Validation](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/validation.md)
* [Virtual Account](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/virtual-account.md)
* [Account Collection Flow](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/account-collection-flow.md)
* [Payment Flow](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/controllers/payment-flow.md)

## SDK Infrastructure

### Configuration

* [ProxySettings](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/proxy-settings.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/environment-based-client-initialization.md)
* [AbstractLogger](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/abstract-logger.md)
* [LoggingConfiguration](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/logging-configuration.md)
* [RequestLoggingConfiguration](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/request-logging-configuration.md)
* [ResponseLoggingConfiguration](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/response-logging-configuration.md)

### HTTP

* [HttpResponse](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/http-response.md)
* [HttpRequest](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/api-response.md)
* [ApiHelper](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/api-helper.md)
* [HttpDateTime](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/http-date-time.md)
* [RFC3339DateTime](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/rfc3339-date-time.md)
* [UnixDateTime](https://www.github.com/sdks-io/mt-python-sdk/tree/0.0.4/doc/unix-date-time.md)



# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| http_client_instance | `Union[Session, HttpClientProvider]` | The Http Client passed from the sdk user for making requests |
| override_http_client_configuration | `bool` | The value which determines to override properties of the passed Http Client from the sdk user |
| http_call_back | `HttpCallBack` | The callback value that is invoked before and after an HTTP call is made to an endpoint |
| timeout | `float` | The value to use for connection timeout. <br> **Default: 30** |
| max_retries | `int` | The number of times to retry an endpoint call if it fails. <br> **Default: 0** |
| backoff_factor | `float` | A backoff factor to apply between attempts after the second try. <br> **Default: 2** |
| retry_statuses | `Array of int` | The http statuses on which retry is to be done. <br> **Default: [408, 413, 429, 500, 502, 503, 504, 521, 522, 524]** |
| retry_methods | `Array of string` | The http methods on which retry is to be done. <br> **Default: ["GET", "PUT"]** |
| proxy_settings | [`ProxySettings`](../doc/proxy-settings.md) | Optional proxy configuration to route HTTP requests through a proxy server. |
| logging_configuration | [`LoggingConfiguration`](../doc/logging-configuration.md) | The SDK logging configuration for API calls |
| basic_auth_credentials | [`BasicAuthCredentials`](auth/basic-authentication.md) | The credential object for Basic Authentication |

The API client can be initialized as follows:

## Code-Based Client Initialization

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

## Environment-Based Client Initialization

```python
from moderntreasury.moderntreasury_client import ModerntreasuryClient

# Specify the path to your .env file if it’s located outside the project’s root directory.
client = ModerntreasuryClient.from_environment(dotenv_path='/path/to/.env')
```

See the [Environment-Based Client Initialization](../doc/environment-based-client-initialization.md) section for details.

## Modern Treasury Client

The gateway for the SDK. This class acts as a factory for the Apis and also holds the configuration of the SDK.

## Apis

| Name | Description |
|  --- | --- |
| account_detail | Gets AccountDetailApi |
| balance_report | Gets BalanceReportApi |
| connection | Gets ConnectionApi |
| counterparty | Gets CounterpartyApi |
| document | Gets DocumentApi |
| event | Gets EventApi |
| expected_payment | Gets ExpectedPaymentApi |
| external_account | Gets ExternalAccountApi |
| incoming_payment_detail | Gets IncomingPaymentDetailApi |
| internal_account | Gets InternalAccountApi |
| invoice_line_item | Gets InvoiceLineItemApi |
| invoice | Gets InvoiceApi |
| ledger_account_category | Gets LedgerAccountCategoryApi |
| ledger_account_payout | Gets LedgerAccountPayoutApi |
| ledger_account_statement | Gets LedgerAccountStatementApi |
| ledger_account | Gets LedgerAccountApi |
| ledger_entry | Gets LedgerEntryApi |
| ledger_event_handler | Gets LedgerEventHandlerApi |
| ledger_transaction | Gets LedgerTransactionApi |
| ledgerable_event | Gets LedgerableEventApi |
| ledger | Gets LedgerApi |
| line_item | Gets LineItemApi |
| paper_item | Gets PaperItemApi |
| payment_order | Gets PaymentOrderApi |
| payment_reference | Gets PaymentReferenceApi |
| ping | Gets PingApi |
| mreturn | Gets ReturnApi |
| reversal | Gets ReversalApi |
| routing_detail | Gets RoutingDetailApi |
| transaction_line_item | Gets TransactionLineItemApi |
| transaction | Gets TransactionApi |
| validation | Gets ValidationApi |
| virtual_account | Gets VirtualAccountApi |
| account_collection_flow | Gets AccountCollectionFlowApi |
| payment_flow | Gets PaymentFlowApi |


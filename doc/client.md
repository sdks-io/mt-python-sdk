
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| http_client_instance | `Union[Session, HttpClientProvider]` | The Http Client passed from the sdk user for making requests |
| override_http_client_configuration | `bool` | The value which determines to override properties of the passed Http Client from the sdk user |
| http_call_back | `HttpCallBack` | The callback value that is invoked before and after an HTTP call is made to an endpoint |
| timeout | `float` | The value to use for connection timeout. <br> **Default: 60** |
| max_retries | `int` | The number of times to retry an endpoint call if it fails. <br> **Default: 0** |
| backoff_factor | `float` | A backoff factor to apply between attempts after the second try. <br> **Default: 2** |
| retry_statuses | `Array of int` | The http statuses on which retry is to be done. <br> **Default: [408, 413, 429, 500, 502, 503, 504, 521, 522, 524]** |
| retry_methods | `Array of string` | The http methods on which retry is to be done. <br> **Default: ["GET", "PUT"]** |
| proxy_settings | [`ProxySettings`](../doc/proxy-settings.md) | Optional proxy configuration to route HTTP requests through a proxy server. |
| basic_auth_credentials | [`BasicAuthCredentials`](auth/basic-authentication.md) | The credential object for Basic Authentication |

The API client can be initialized as follows:

## Code-Based Client Initialization

```python
from moderntreasury.configuration import Environment
from moderntreasury.http.auth.basic_auth import BasicAuthCredentials
from moderntreasury.moderntreasury_client import ModerntreasuryClient

client = ModerntreasuryClient(
    basic_auth_credentials=BasicAuthCredentials(
        username='BasicAuthUserName',
        password='BasicAuthPassword'
    ),
    environment=Environment.PRODUCTION
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

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

## Controllers

| Name | Description |
|  --- | --- |
| account_detail | Gets AccountDetailController |
| balance_report | Gets BalanceReportController |
| connection | Gets ConnectionController |
| counterparty | Gets CounterpartyController |
| document | Gets DocumentController |
| event | Gets EventController |
| expected_payment | Gets ExpectedPaymentController |
| external_account | Gets ExternalAccountController |
| incoming_payment_detail | Gets IncomingPaymentDetailController |
| internal_account | Gets InternalAccountController |
| invoice_line_item | Gets InvoiceLineItemController |
| invoice | Gets InvoiceController |
| ledger_account_category | Gets LedgerAccountCategoryController |
| ledger_account_payout | Gets LedgerAccountPayoutController |
| ledger_account_statement | Gets LedgerAccountStatementController |
| ledger_account | Gets LedgerAccountController |
| ledger_entry | Gets LedgerEntryController |
| ledger_event_handler | Gets LedgerEventHandlerController |
| ledger_transaction | Gets LedgerTransactionController |
| ledgerable_event | Gets LedgerableEventController |
| ledger | Gets LedgerController |
| line_item | Gets LineItemController |
| paper_item | Gets PaperItemController |
| payment_order | Gets PaymentOrderController |
| payment_reference | Gets PaymentReferenceController |
| ping | Gets PingController |
| mreturn | Gets ReturnController |
| reversal | Gets ReversalController |
| routing_detail | Gets RoutingDetailController |
| transaction_line_item | Gets TransactionLineItemController |
| transaction | Gets TransactionController |
| validation | Gets ValidationController |
| virtual_account | Gets VirtualAccountController |
| account_collection_flow | Gets AccountCollectionFlowController |
| payment_flow | Gets PaymentFlowController |


# Payment Order

```python
payment_order_api = client.payment_order
```

## Class Name

`PaymentOrderApi`

## Methods

* [Create Async Payment Order](../../doc/controllers/payment-order.md#create-async-payment-order)
* [List Payment Orders](../../doc/controllers/payment-order.md#list-payment-orders)
* [Create Payment Order](../../doc/controllers/payment-order.md#create-payment-order)
* [Get Payment Order](../../doc/controllers/payment-order.md#get-payment-order)
* [Update Payment Order](../../doc/controllers/payment-order.md#update-payment-order)


# Create Async Payment Order

Create a new payment order asynchronously

```python
def create_async_payment_order(self,
                              idempotency_key=None,
                              body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `body` | [`PaymentOrderAsyncCreateRequest`](../../doc/models/payment-order-async-create-request.md) | Body, Optional | - |

## Response Type

**202**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AsyncResponse`](../../doc/models/async-response.md).

## Example Usage

```python
body = PaymentOrderAsyncCreateRequest(
    mtype=Type5.NEFT,
    amount=218,
    direction=Direction5.CREDIT,
    originating_account_id='000022b4-0000-0000-0000-000000000000',
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = payment_order_api.create_async_payment_order(
    body=body
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# List Payment Orders

Get a list of all payment orders

```python
def list_payment_orders(self,
                       after_cursor=None,
                       per_page=None,
                       mtype=None,
                       priority=None,
                       counterparty_id=None,
                       originating_account_id=None,
                       transaction_id=None,
                       status=None,
                       direction=None,
                       reference_number=None,
                       effective_date_start=None,
                       effective_date_end=None,
                       metadata=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |
| `mtype` | [`Type13`](../../doc/models/type-13.md) | Query, Optional | - |
| `priority` | [`Priority4`](../../doc/models/priority-4.md) | Query, Optional | Either `normal` or `high`. For ACH and EFT payments, `high` represents a same-day ACH or EFT transfer, respectively. For check payments, `high` can mean an overnight check rather than standard mail. |
| `counterparty_id` | `uuid\|str` | Query, Optional | - |
| `originating_account_id` | `uuid\|str` | Query, Optional | - |
| `transaction_id` | `uuid\|str` | Query, Optional | The ID of a transaction that the payment order has been reconciled to. |
| `status` | [`Status24`](../../doc/models/status-24.md) | Query, Optional | - |
| `direction` | [`Direction15`](../../doc/models/direction-15.md) | Query, Optional | - |
| `reference_number` | `str` | Query, Optional | Query for records with the provided reference number |
| `effective_date_start` | `date` | Query, Optional | An inclusive lower bound for searching effective_date |
| `effective_date_end` | `date` | Query, Optional | An inclusive upper bound for searching effective_date |
| `metadata` | `Dict[str, str]` | Query, Optional | For example, if you want to query for records with metadata key `Type` and value `Loan`, the query would be `metadata%5BType%5D=Loan`. This encodes the query parameters. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[PaymentOrder]`](../../doc/models/payment-order.md).

## Example Usage

```python
result = payment_order_api.list_payment_orders()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Payment Order

Create a new Payment Order

```python
def create_payment_order(self,
                        mtype,
                        amount,
                        direction,
                        originating_account_id,
                        content_type=None,
                        idempotency_key=None,
                        subtype=None,
                        priority=None,
                        receiving_account_id=None,
                        accounting=None,
                        accounting_category_id=None,
                        accounting_ledger_class_id=None,
                        currency=None,
                        effective_date=None,
                        description=None,
                        statement_descriptor=None,
                        remittance_information=None,
                        purpose=None,
                        metadata=None,
                        charge_bearer=None,
                        foreign_exchange_indicator=None,
                        foreign_exchange_contract=None,
                        nsf_protected=None,
                        originating_party_name=None,
                        ultimate_originating_party_name=None,
                        ultimate_originating_party_identifier=None,
                        ultimate_receiving_party_name=None,
                        ultimate_receiving_party_identifier=None,
                        send_remittance_advice=None,
                        expires_at=None,
                        fallback_type=None,
                        receiving_account=None,
                        ledger_transaction=None,
                        line_items=None,
                        transaction_monitoring_enabled=None,
                        documents=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mtype` | [`Type5`](../../doc/models/type-5.md) | Form, Required | One of `ach`, `eft`, `wire`, `check`, `sen`, `book`, `rtp`, `sepa`, `bacs`, `au_becs`, `interac`, `signet`, `provexchange`. |
| `amount` | `int` | Form, Required | Value in specified currency's smallest unit. e.g. $10 would be represented as 1000 (cents). For RTP, the maximum amount allowed by the network is $100,000. |
| `direction` | [`Direction5`](../../doc/models/direction-5.md) | Form, Required | One of `credit`, `debit`. Describes the direction money is flowing in the transaction. A `credit` moves money from your account to someone else's. A `debit` pulls money from someone else's account to your own. Note that wire, rtp, and check payments will always be `credit`. |
| `originating_account_id` | `uuid\|str` | Form, Required | The ID of one of your organization's internal accounts. |
| `content_type` | [`ContentType`](../../doc/models/content-type.md) | Header, Optional | - |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `subtype` | [`Subtype`](../../doc/models/subtype.md) | Form, Optional | An additional layer of classification for the type of payment order you are doing. This field is only used for `ach` payment orders currently. For `ach`  payment orders, the `subtype`  represents the SEC code. We currently support `CCD`, `PPD`, `IAT`, `CTX`, `WEB`, `CIE`, and `TEL`. |
| `priority` | [`Priority`](../../doc/models/priority.md) | Form, Optional | Either `normal` or `high`. For ACH and EFT payments, `high` represents a same-day ACH or EFT transfer, respectively. For check payments, `high` can mean an overnight check rather than standard mail. |
| `receiving_account_id` | `uuid\|str` | Form, Optional | Either `receiving_account` or `receiving_account_id` must be present. When using `receiving_account_id`, you may pass the id of an external account or an internal account. |
| `accounting` | [`Accounting`](../../doc/models/accounting.md) | Form, Optional | - |
| `accounting_category_id` | `uuid\|str` | Form, Optional | The ID of one of your accounting categories. Note that these will only be accessible if your accounting system has been connected. |
| `accounting_ledger_class_id` | `uuid\|str` | Form, Optional | The ID of one of your accounting ledger classes. Note that these will only be accessible if your accounting system has been connected. |
| `currency` | [`Currency`](../../doc/models/currency.md) | Form, Optional | Three-letter ISO currency code. |
| `effective_date` | `date` | Form, Optional | Date transactions are to be posted to the participants' account. Defaults to the current business day or the next business day if the current day is a bank holiday or weekend. Format: yyyy-mm-dd. |
| `description` | `str` | Form, Optional | An optional description for internal use. |
| `statement_descriptor` | `str` | Form, Optional | An optional descriptor which will appear in the receiver's statement. For `check` payments this field will be used as the memo line. For `ach` the maximum length is 10 characters. Note that for ACH payments, the name on your bank account will be included automatically by the bank, so you can use the characters for other useful information. For `eft` the maximum length is 15 characters. |
| `remittance_information` | `str` | Form, Optional | For `ach`, this field will be passed through on an addenda record. For `wire` payments the field will be passed through as the "Originator to Beneficiary Information", also known as OBI or Fedwire tag 6000. |
| `purpose` | `str` | Form, Optional | For `wire`, this is usually the purpose which is transmitted via the "InstrForDbtrAgt" field in the ISO20022 file. If you are using Currencycloud, this is the `payment.purpose_code` field. For `eft`, this field is the 3 digit CPA Code that will be attached to the payment. |
| `metadata` | `Dict[str, str]` | Form, Optional | Additional data represented as key-value pairs. Both the key and value must be strings. |
| `charge_bearer` | [`ChargeBearer`](../../doc/models/charge-bearer.md) | Form, Optional | The party that will pay the fees for the payment order. Only applies to wire payment orders. Can be one of shared, sender, or receiver, which correspond respectively with the SWIFT 71A values `SHA`, `OUR`, `BEN`. |
| `foreign_exchange_indicator` | [`ForeignExchangeIndicator`](../../doc/models/foreign-exchange-indicator.md) | Form, Optional | Indicates the type of FX transfer to initiate, can be either `variable_to_fixed`, `fixed_to_variable`, or `null` if the payment order currency matches the originating account currency. |
| `foreign_exchange_contract` | `str` | Form, Optional | If present, indicates a specific foreign exchange contract number that has been generated by your financial institution. |
| `nsf_protected` | `bool` | Form, Optional | A boolean to determine if NSF Protection is enabled for this payment order. Note that this setting must also be turned on in your organization settings page. |
| `originating_party_name` | `str` | Form, Optional | If present, this will replace your default company name on receiver's bank statement. This field can only be used for ACH payments currently. For ACH, only the first 16 characters of this string will be used. Any additional characters will be truncated. |
| `ultimate_originating_party_name` | `str` | Form, Optional | Name of the ultimate originator of the payment order. |
| `ultimate_originating_party_identifier` | `str` | Form, Optional | Identifier of the ultimate originator of the payment order. |
| `ultimate_receiving_party_name` | `str` | Form, Optional | Name of the ultimate funds recipient. |
| `ultimate_receiving_party_identifier` | `str` | Form, Optional | Identifier of the ultimate funds recipient. |
| `send_remittance_advice` | `bool` | Form, Optional | Send an email to the counterparty when the payment order is sent to the bank. If `null`, `send_remittance_advice` on the Counterparty is used. |
| `expires_at` | `datetime` | Form, Optional | RFP payments require an expires_at. This value must be past the effective_date. |
| `fallback_type` | [`FallbackType`](../../doc/models/fallback-type.md) | Form, Optional | A payment type to fallback to if the original type is not valid for the receiving account. Currently, this only supports falling back from RTP to ACH (type=rtp and fallback_type=ach) |
| `receiving_account` | [`ReceivingAccount1`](../../doc/models/receiving-account-1.md) | Form, Optional | Either `receiving_account` or `receiving_account_id` must be present. When using `receiving_account_id`, you may pass the id of an external account or an internal account. |
| `ledger_transaction` | [`LedgerTransactionCreateRequest`](../../doc/models/ledger-transaction-create-request.md) | Form, Optional | - |
| `line_items` | [`List[LineItemRequest]`](../../doc/models/line-item-request.md) | Form, Optional | An array of line items that must sum up to the amount of the payment order. |
| `transaction_monitoring_enabled` | `bool` | Form, Optional | A flag that determines whether a payment order should go through transaction monitoring. |
| `documents` | [`List[DocumentCreateRequest]`](../../doc/models/document-create-request.md) | Form, Optional | An array of documents to be attached to the payment order. Note that if you attach documents, the request's content type must be `multipart/form-data`. |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PaymentOrder`](../../doc/models/payment-order.md).

## Example Usage

```python
mtype = Type5.BOOK

amount = 46

direction = Direction5.CREDIT

originating_account_id = '0000099c-0000-0000-0000-000000000000'

receiving_account = ReceivingAccount1(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

ledger_transaction = LedgerTransactionCreateRequest(
    ledger_entries=[
        LedgerEntryCreateRequest(
            amount=60,
            direction=Direction5.CREDIT,
            ledger_account_id='00002600-0000-0000-0000-000000000000',
            metadata={
                'key': 'value',
                'foo': 'bar',
                'modern': 'treasury'
            }
        )
    ],
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

line_items = [
    LineItemRequest(
        amount=244,
        metadata={
            'key': 'value',
            'foo': 'bar',
            'modern': 'treasury'
        }
    )
]

documents = [
    DocumentCreateRequest(
        documentable_id='documentable_id6',
        documentable_type=DocumentableType1.CONNECTIONS,
        file=None
    )
]

result = payment_order_api.create_payment_order(
    mtype,
    amount,
    direction,
    originating_account_id,
    receiving_account=receiving_account,
    ledger_transaction=ledger_transaction,
    line_items=line_items,
    documents=documents
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | parameter_invalid | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 401 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 422 | unsuccessful | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Payment Order

Get details on a single payment order

```python
def get_payment_order(self,
                     id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PaymentOrder`](../../doc/models/payment-order.md).

## Example Usage

```python
id = 'id0'

result = payment_order_api.get_payment_order(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Update Payment Order

Update a payment order

```python
def update_payment_order(self,
                        id,
                        body=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `str` | Template, Required | - |
| `body` | [`PaymentOrderUpdateRequest`](../../doc/models/payment-order-update-request.md) | Body, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`PaymentOrder`](../../doc/models/payment-order.md).

## Example Usage

```python
id = 'id0'

body = PaymentOrderUpdateRequest(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)

result = payment_order_api.update_payment_order(
    id,
    body=body
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
| 422 | parameter_invalid | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


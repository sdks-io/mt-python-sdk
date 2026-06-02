# Document

```python
document_api = client.document
```

## Class Name

`DocumentApi`

## Methods

* [List Documents](../../doc/controllers/document.md#list-documents)
* [Create Document](../../doc/controllers/document.md#create-document)
* [List Documents 1](../../doc/controllers/document.md#list-documents-1)
* [Create Document 1](../../doc/controllers/document.md#create-document-1)
* [Get Document](../../doc/controllers/document.md#get-document)
* [Get Document 1](../../doc/controllers/document.md#get-document-1)
* [Download Document](../../doc/controllers/document.md#download-document)
* [Download Document 1](../../doc/controllers/document.md#download-document-1)


# List Documents

Get a list of documents.

```python
def list_documents(self,
                  documentable_id=None,
                  documentable_type=None,
                  after_cursor=None,
                  per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documentable_id` | `str` | Query, Optional | The unique identifier for the associated object. |
| `documentable_type` | [`DocumentableType2`](../../doc/models/documentable-type-2.md) | Query, Optional | The type of the associated object. Currently can be one of `payment_order`, `transaction`, `paper_item`, `expected_payment`, `counterparty`, `organization`, `case`, `internal_account`, `decision`, or `external_account`. |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[Document]`](../../doc/models/document.md).

## Example Usage

```python
result = document_api.list_documents()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Create Document

Create a document.

```python
def create_document(self,
                   documentable_id,
                   documentable_type,
                   file,
                   idempotency_key=None,
                   document_type=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documentable_id` | `str` | Form, Required | The unique identifier for the associated object. |
| `documentable_type` | [`DocumentableType1`](../../doc/models/documentable-type-1.md) | Form, Required | - |
| `file` | [`typing.BinaryIO`](../../doc/models/file.md) | Form, Required | - |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `document_type` | `str` | Form, Optional | A category given to the document, can be `null`. |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Document`](../../doc/models/document.md).

## Example Usage

```python
documentable_id = 'documentable_id0'

documentable_type = DocumentableType1.PAPER_ITEMS

file = FileWrapper(Path('dummy_file').open('rb'), 'optional-content-type')

result = document_api.create_document(
    documentable_id,
    documentable_type,
    file
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
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# List Documents 1

Get a list of documents.

```python
def list_documents_1(self,
                    documentable_id,
                    documentable_type,
                    document_type=None,
                    after_cursor=None,
                    per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documentable_id` | `str` | Template, Required | The unique identifier for the associated object. |
| `documentable_type` | [`DocumentableType2`](../../doc/models/documentable-type-2.md) | Template, Required | The type of the associated object. Currently can be one of `payment_order`, `transaction`, `paper_item`, `expected_payment`, `counterparty`, `organization`, `case`, `internal_account`, `decision`, or `external_account`. |
| `document_type` | `str` | Query, Optional | A category given to the document, can be `null`. |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[Document]`](../../doc/models/document.md).

## Example Usage

```python
documentable_id = 'documentable_id0'

documentable_type = DocumentableType2.PAPER_ITEMS

result = document_api.list_documents_1(
    documentable_id,
    documentable_type
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```


# Create Document 1

Create a document.

```python
def create_document_1(self,
                     documentable_id,
                     documentable_type,
                     file,
                     idempotency_key=None,
                     document_type=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documentable_id` | `str` | Template, Required | The unique identifier for the associated object. |
| `documentable_type` | [`DocumentableType2`](../../doc/models/documentable-type-2.md) | Template, Required | The type of the associated object. Currently can be one of `payment_order`, `transaction`, `paper_item`, `expected_payment`, `counterparty`, `organization`, `case`, `internal_account`, `decision`, or `external_account`. |
| `file` | [`typing.BinaryIO`](../../doc/models/file.md) | Form, Required | - |
| `idempotency_key` | `str` | Header, Optional | This key should be something unique, preferably something like an UUID. |
| `document_type` | `str` | Form, Optional | A category given to the document, can be `null`. |

## Response Type

**201**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Document`](../../doc/models/document.md).

## Example Usage

```python
documentable_id = 'documentable_id0'

documentable_type = DocumentableType2.PAPER_ITEMS

file = FileWrapper(Path('dummy_file').open('rb'), 'optional-content-type')

result = document_api.create_document_1(
    documentable_id,
    documentable_type,
    file
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
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Document

Get an existing document.

```python
def get_document(self,
                documentable_id,
                documentable_type,
                id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documentable_id` | `str` | Template, Required | The unique identifier for the associated object. |
| `documentable_type` | [`DocumentableType2`](../../doc/models/documentable-type-2.md) | Template, Required | The type of the associated object. Currently can be one of `payment_order`, `transaction`, `paper_item`, `expected_payment`, `counterparty`, `organization`, `case`, `internal_account`, `decision`, or `external_account`. |
| `id` | `uuid\|str` | Template, Required | The ID of the document. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Document`](../../doc/models/document.md).

## Example Usage

```python
documentable_id = 'documentable_id0'

documentable_type = DocumentableType2.PAPER_ITEMS

id = '00001770-0000-0000-0000-000000000000'

result = document_api.get_document(
    documentable_id,
    documentable_type,
    id
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


# Get Document 1

Get an existing document.

```python
def get_document_1(self,
                  id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Template, Required | The ID of the document. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`Document`](../../doc/models/document.md).

## Example Usage

```python
id = '00001770-0000-0000-0000-000000000000'

result = document_api.get_document_1(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Download Document

Download an existing document.

```python
def download_document(self,
                     documentable_id,
                     documentable_type,
                     id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `documentable_id` | `str` | Template, Required | The unique identifier for the associated object. |
| `documentable_type` | [`DocumentableType2`](../../doc/models/documentable-type-2.md) | Template, Required | The type of the associated object. Currently can be one of `payment_order`, `transaction`, `paper_item`, `expected_payment`, `counterparty`, `organization`, `case`, `internal_account`, `decision`, or `external_account`. |
| `id` | `uuid\|str` | Template, Required | The ID of the document. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
documentable_id = 'documentable_id0'

documentable_type = DocumentableType2.PAPER_ITEMS

id = '00001770-0000-0000-0000-000000000000'

result = document_api.download_document(
    documentable_id,
    documentable_type,
    id
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
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Download Document 1

Download an existing document.

```python
def download_document_1(self,
                       id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `uuid\|str` | Template, Required | The ID of the document. |

## Response Type

**200**

This method returns an [`ApiResponse`](../../doc/api-response.md) instance.

## Example Usage

```python
id = '00001770-0000-0000-0000-000000000000'

result = document_api.download_document_1(id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |
| 404 | not found | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


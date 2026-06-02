# Balance Report

```python
balance_report_controller = client.balance_report
```

## Class Name

`BalanceReportController`

## Methods

* [List Balance Reports](../../doc/controllers/balance-report.md#list-balance-reports)
* [Get Balance Report](../../doc/controllers/balance-report.md#get-balance-report)


# List Balance Reports

Get all balance reports for a given internal account.

```python
def list_balance_reports(self,
                        internal_account_id,
                        as_of_date=None,
                        balance_report_type=None,
                        after_cursor=None,
                        per_page=None)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `internal_account_id` | `str` | Template, Required | - |
| `as_of_date` | `date` | Query, Optional | The date of the balance report in local time. |
| `balance_report_type` | [`BalanceReportType1`](../../doc/models/balance-report-type-1.md) | Query, Optional | The specific type of balance report. One of `intraday`, `previous_day`, `real_time`, or `other`. |
| `after_cursor` | `str` | Query, Optional | - |
| `per_page` | `int` | Query, Optional | - |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`List[BalanceReport]`](../../doc/models/balance-report.md).

## Example Usage

```python
internal_account_id = 'internal_account_id4'

result = balance_report_controller.list_balance_reports(internal_account_id)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | forbidden | [`ErrorMessageException`](../../doc/models/error-message-exception.md) |


# Get Balance Report

Get a single balance report for a given internal account.

```python
def get_balance_report(self,
                      internal_account_id,
                      id)
```

## Authentication

This endpoint requires [basic_auth](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `internal_account_id` | `str` | Template, Required | - |
| `id` | `str` | Template, Required | Either the unique identifier of the balance report or latest for the latest balance report. |

## Response Type

**200**: successful

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`BalanceReport`](../../doc/models/balance-report.md).

## Example Usage

```python
internal_account_id = 'internal_account_id4'

id = 'id0'

result = balance_report_controller.get_balance_report(
    internal_account_id,
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


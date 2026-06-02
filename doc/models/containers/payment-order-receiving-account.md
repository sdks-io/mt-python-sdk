
# Payment Order Receiving Account

## Data Type

`ReceivingAccount | InternalAccount`

## Cases

| Type |
|  --- |
| [`ReceivingAccount`](../../../doc/models/receiving-account.md) |
| [`InternalAccount`](../../../doc/models/internal-account.md) |

## ReceivingAccount

### Initialization Code

#### Example

```python
value = ReceivingAccount(
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    }
)
```

## InternalAccount

### Initialization Code

#### Example

```python
value = InternalAccount(
    id='0000086e-0000-0000-0000-000000000000',
    object='object6',
    live_mode=False,
    created_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
    updated_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
    account_type=AccountType5.SAVINGS,
    party_name='party_name0',
    party_type=PartyType5.BUSINESS,
    party_address=Address(
        id='00000cb8-0000-0000-0000-000000000000',
        object='object6',
        live_mode=False,
        created_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
        updated_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
        line_1='line18',
        line_2='line20',
        locality='locality6',
        region='region2',
        postal_code='postal_code8',
        country='country0'
    ),
    name='name8',
    account_details=[
        AccountDetail(
            id='00000bf8-0000-0000-0000-000000000000',
            object='object8',
            live_mode=False,
            created_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
            updated_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
            discarded_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
            account_number_type=AccountNumberType.OTHER,
            account_number_safe='account_number_safe6'
        )
    ],
    routing_details=[
        RoutingDetail(
            id='00001b96-0000-0000-0000-000000000000',
            object='object0',
            live_mode=False,
            created_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
            updated_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
            discarded_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
            routing_number='routing_number6',
            routing_number_type=RoutingNumberType.GB_SORT_CODE,
            payment_type=PaymentType1.EFT,
            bank_name='bank_name2',
            bank_address=Address(
                id='000004a8-0000-0000-0000-000000000000',
                object='object0',
                live_mode=False,
                created_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
                updated_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
                line_1='line14',
                line_2='line26',
                locality='locality2',
                region='region8',
                postal_code='postal_code4',
                country='country6'
            )
        )
    ],
    connection=Connection(
        id='00001eee-0000-0000-0000-000000000000',
        object='object4',
        live_mode=False,
        created_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
        updated_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
        discarded_at=dateutil.parser.parse('2016-03-13T12:52:32.123Z'),
        vendor_id='00002026-0000-0000-0000-000000000000',
        vendor_customer_id='0000080c-0000-0000-0000-000000000000',
        vendor_name='vendor_name0'
    ),
    currency=Currency.EGP,
    metadata={
        'key': 'value',
        'foo': 'bar',
        'modern': 'treasury'
    },
    parent_account_id='0000052e-0000-0000-0000-000000000000',
    counterparty_id='0000001a-0000-0000-0000-000000000000',
    ledger_account_id='00001cf4-0000-0000-0000-000000000000'
)
```


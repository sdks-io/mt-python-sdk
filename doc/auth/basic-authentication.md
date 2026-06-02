
# Basic Authentication



Documentation for accessing and setting credentials for basic_auth.

## Auth Credentials

| Name | Type | Description | Getter |
|  --- | --- | --- | --- |
| BasicAuthUserName | `str` | The username to use with basic authentication | `username` |
| BasicAuthPassword | `str` | The password to use with basic authentication | `password` |



**Note:** Auth credentials can be set using `BasicAuthCredentials` object, passed in as named parameter `basic_auth_credentials` in the client initialization.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```python
from moderntreasury.http.auth.basic_auth import BasicAuthCredentials
from moderntreasury.moderntreasury_client import ModerntreasuryClient

client = ModerntreasuryClient(
    basic_auth_credentials=BasicAuthCredentials(
        username='BasicAuthUserName',
        password='BasicAuthPassword'
    )
)
```



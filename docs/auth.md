#### Reference file : auth.proto
<a name="auth-v1-LoginReq"></a>

### LoginReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| username | [string](#string) |  | public DID |
| password | [string](#string) |  | signed public DID &#43; requestTime from the edge agent |
| requestTime | [int64](#int64) |  | edge agent&#39;s unix int64 UTC timestamp |






<a name="auth-v1-LoginRes"></a>

### LoginRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  |  |






<a name="auth-v1-RefreshTokenReq"></a>

### RefreshTokenReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| oldToken | [string](#string) |  |  |






<a name="auth-v1-RefreshTokenRes"></a>

### RefreshTokenRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| newToken | [string](#string) |  |  |






<a name="auth-v1-SetInitialPassphraseReq"></a>

### SetInitialPassphraseReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| passphrase | [string](#string) |  |  |






<a name="auth-v1-SetInitialPassphraseRes"></a>

### SetInitialPassphraseRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  |  |






<a name="auth-v1-VerifyTokenReq"></a>

### VerifyTokenReq
Expects token received post login / refresh process


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  |  |






<a name="auth-v1-VerifyTokenRes"></a>

### VerifyTokenRes
returns True if token is valid, else false


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| res | [bool](#bool) |  |  |





 

 

 


<a name="auth-v1-Auth"></a>

### Auth
Auth defines authentication service

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Login | [LoginReq](#auth-v1-LoginReq) | [LoginRes](#auth-v1-LoginRes) |  |
| SetInitialPassphrase | [SetInitialPassphraseReq](#auth-v1-SetInitialPassphraseReq) | [SetInitialPassphraseRes](#auth-v1-SetInitialPassphraseRes) |  |
| RefreshToken | [RefreshTokenReq](#auth-v1-RefreshTokenReq) | [RefreshTokenRes](#auth-v1-RefreshTokenRes) |  |
| VerifyToken | [VerifyTokenReq](#auth-v1-VerifyTokenReq) | [VerifyTokenRes](#auth-v1-VerifyTokenRes) |  |

 



## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |


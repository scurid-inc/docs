# MicroScurid Documentation
<a name="top"></a>

## Table of Contents

- [microscurid.proto](#microscurid-proto)
    - [Login](#microscurid-v0-Login)
    - [LoginRes](#microscurid-v0-LoginRes)
    - [RegisterDeviceIdentity](#microscurid-v0-RegisterDeviceIdentity)
    - [RegisterDeviceIdentityRes](#microscurid-v0-RegisterDeviceIdentityRes)
    - [ReqMetadata](#microscurid-v0-ReqMetadata)
    - [VerifySignature](#microscurid-v0-VerifySignature)
  
    - [ReqMetadata.ReqType](#microscurid-v0-ReqMetadata-ReqType)
  
- [Scalar Value Types](#scalar-value-types)



<a name="microscurid-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## microscurid.proto



<a name="microscurid-v0-Login"></a>

### Login
Used for log in


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| username | [string](#string) |  | public DID |






<a name="microscurid-v0-LoginRes"></a>

### LoginRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  | short lived encrypted token returned by the server on successful login |






<a name="microscurid-v0-RegisterDeviceIdentity"></a>

### RegisterDeviceIdentity
RegisterDeviceIdentity contains the required structure to register a newly generated Identity on the hardware
TODO: Enhance with other hardware details to include DeviceContext


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  | DID generated on the device |
| unixTime | [int64](#int64) |  | time of request |
| deviceName | [string](#string) |  | device name provided by the user |






<a name="microscurid-v0-RegisterDeviceIdentityRes"></a>

### RegisterDeviceIdentityRes
RegisterDeviceIdentityRes returns required response.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  |  |






<a name="microscurid-v0-ReqMetadata"></a>

### ReqMetadata



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| reqType | [ReqMetadata.ReqType](#microscurid-v0-ReqMetadata-ReqType) |  |  |
| registerDeviceIdentity | [RegisterDeviceIdentity](#microscurid-v0-RegisterDeviceIdentity) | optional |  |
| verifySignature | [VerifySignature](#microscurid-v0-VerifySignature) | optional |  |
| login | [Login](#microscurid-v0-Login) | optional |  |






<a name="microscurid-v0-VerifySignature"></a>

### VerifySignature



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  | TODO add data later |





 


<a name="microscurid-v0-ReqMetadata-ReqType"></a>

### ReqMetadata.ReqType


| Name | Number | Description |
| ---- | ------ | ----------- |
| UnknownReq | 0 | UnknownReq, default fallback field in case unknown enum information is sent from the MicroScurid |
| IdentityRegistration | 1 | IdentityRegistration, used for registering an incoming request with DID (identity) from the device via MicroScurid |
| Verify | 2 | Verify, used for verifying the signature coming along with the identity and the |


 

 

 



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


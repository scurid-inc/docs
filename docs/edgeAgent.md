These are the set of APIs that are exposed when running `Scurid Edge Agent` on an IoT device.

## ScuridEdgeAgentAPI Endpoint group

#### Reference filename : edgeagent.proto

<a name="edgeagentapis-v1-CreateDeviceIdentityReq"></a>

### CreateDeviceIdentityReq
left blank intentionally

<a name="edgeagentapis-v1-CreateDeviceIdentityRes"></a>

### CreateDeviceIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |






<a name="edgeagentapis-v1-DeleteDeviceIdentityReq"></a>

### DeleteDeviceIdentityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |






<a name="edgeagentapis-v1-DeleteDeviceIdentityRes"></a>

### DeleteDeviceIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  |  |






<a name="edgeagentapis-v1-DownloadFilesReq"></a>

### DownloadFilesReq
request structure to be sent


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| identity | [string](#string) |  | device&#39;s public identity |
| path | [string](#string) |  | where ever user wants to store the files |






<a name="edgeagentapis-v1-DownloadFilesRes"></a>

### DownloadFilesRes
true if all files are downloaded, else false - check error for details


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | True/False, confirms if the files have been downloaded, check for error if false |






<a name="edgeagentapis-v1-Empty"></a>

### Empty
left blank






<a name="edgeagentapis-v1-GetDeviceIdentityReq"></a>

### GetDeviceIdentityReq
DID to be checked if it exists


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |






<a name="edgeagentapis-v1-GetDeviceIdentityRes"></a>

### GetDeviceIdentityRes
provides validation that device&#39;s DID is already generated


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |






<a name="edgeagentapis-v1-GetOnboardingPackageReq"></a>

### GetOnboardingPackageReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  | public DID |






<a name="edgeagentapis-v1-GetOnboardingPackageRes"></a>

### GetOnboardingPackageRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| onboardingPkg | [string](#string) |  | can contain any kind of on boarding information, JSON, XML etc. |






<a name="edgeagentapis-v1-GetScuridEdgeAgentVersionRes"></a>

### GetScuridEdgeAgentVersionRes
provides what agent version is currently installed on the hardware


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentVersion | [string](#string) |  |  |






<a name="edgeagentapis-v1-GetTokenReq"></a>

### GetTokenReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| username | [string](#string) |  | public DID |






<a name="edgeagentapis-v1-GetTokenRes"></a>

### GetTokenRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| token | [string](#string) |  | short lived encrypted token returned by the server on successful login |






<a name="edgeagentapis-v1-RegisterDeviceIdentityReq"></a>

### RegisterDeviceIdentityReq
sent by any client using the edge agent for generating the identity
req expects fields of type GetDeviceIdentityReq and GetScuridEdgeAgentVersionRes


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  | public identity of DID |
| unixTime | [int64](#int64) |  | time of request |
| deviceName | [string](#string) |  | device name provided by the Iot Software interacting with the agent |






<a name="edgeagentapis-v1-RegisterDeviceIdentityRes"></a>

### RegisterDeviceIdentityRes
Response for registration request from the caller


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | simply a confirmation if request has been received or not |






<a name="edgeagentapis-v1-SignBytePayloadWithIdentityReq"></a>

### SignBytePayloadWithIdentityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| payload | [bytes](#bytes) |  | array if bytes to be signed |
| did | [string](#string) |  | identity i.e. did:scurid:XXXXXXXXXXX ; NOTE identity is case sensitive |






<a name="edgeagentapis-v1-SignBytePayloadWithIdentityRes"></a>

### SignBytePayloadWithIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  | generated signature |






<a name="edgeagentapis-v1-SignWithIdentityReq"></a>

### SignWithIdentityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| payload | [string](#string) |  | data to be signed |
| did | [string](#string) |  | identity i.e. did:scurid:XXXXXXXXXXX ; note identity is case sensitive |






<a name="edgeagentapis-v1-SignWithIdentityRes"></a>

### SignWithIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  | generated signature |






<a name="edgeagentapis-v1-VerifyBytePayloadWithIdentityReq"></a>

### VerifyBytePayloadWithIdentityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  |  |
| payload | [bytes](#bytes) |  |  |
| did | [string](#string) |  | identity i.e. did:scurid:XXXXXXXXXXX ; NOTE: identity is case sensitive |






<a name="edgeagentapis-v1-VerifyBytePayloadWithIdentityRes"></a>

### VerifyBytePayloadWithIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| isValid | [bool](#bool) |  | true if valid, else false (Defaults to False) |






<a name="edgeagentapis-v1-VerifySignatureReq"></a>

### VerifySignatureReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  |  |
| payload | [string](#string) |  |  |
| did | [string](#string) |  | identity i.e. did:scurid:XXXXXXXXXXX ; note identity is case sensitive |






<a name="edgeagentapis-v1-VerifySignatureRes"></a>

### VerifySignatureRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| isValid | [bool](#bool) |  | true if valid, else false |





 

 

 


<a name="edgeagentapis-v1-ScuridEdgeAgentAPI"></a>

### ScuridEdgeAgentAPI


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| CreateDeviceIdentity | [CreateDeviceIdentityReq](#edgeagentapis-v1-CreateDeviceIdentityReq) | [CreateDeviceIdentityRes](#edgeagentapis-v1-CreateDeviceIdentityRes) | Create an identity |
| DeleteDeviceDID | [DeleteDeviceIdentityReq](#edgeagentapis-v1-DeleteDeviceIdentityReq) | [DeleteDeviceIdentityRes](#edgeagentapis-v1-DeleteDeviceIdentityRes) | Delete an existing DID |
| GetDeviceIdentity | [GetDeviceIdentityReq](#edgeagentapis-v1-GetDeviceIdentityReq) | [GetDeviceIdentityRes](#edgeagentapis-v1-GetDeviceIdentityRes) | Validates if particular identity was already created locally |
| GetScuridEdgeAgentVersion | [Empty](#edgeagentapis-v1-Empty) | [GetScuridEdgeAgentVersionRes](#edgeagentapis-v1-GetScuridEdgeAgentVersionRes) | Get currently installed version of edge agent |
| SignWithIdentity | [SignWithIdentityReq](#edgeagentapis-v1-SignWithIdentityReq) | [SignWithIdentityRes](#edgeagentapis-v1-SignWithIdentityRes) | Signs a payload with identity |
| VerifySignature | [VerifySignatureReq](#edgeagentapis-v1-VerifySignatureReq) | [VerifySignatureRes](#edgeagentapis-v1-VerifySignatureRes) | Verifies a signature tagged to the payload |
| SignBytePayloadWithIdentity | [SignBytePayloadWithIdentityReq](#edgeagentapis-v1-SignBytePayloadWithIdentityReq) | [SignBytePayloadWithIdentityRes](#edgeagentapis-v1-SignBytePayloadWithIdentityRes) | Signs a byte array payload with identity |
| VerifyBytePayloadWithIdentity | [VerifyBytePayloadWithIdentityReq](#edgeagentapis-v1-VerifyBytePayloadWithIdentityReq) | [VerifyBytePayloadWithIdentityRes](#edgeagentapis-v1-VerifyBytePayloadWithIdentityRes) | Verifies a byte array payload with identity |
| RegisterDeviceIdentity | [RegisterDeviceIdentityReq](#edgeagentapis-v1-RegisterDeviceIdentityReq) | [RegisterDeviceIdentityRes](#edgeagentapis-v1-RegisterDeviceIdentityRes) | To be called for registering the device identity for the first time Expects additional device data that will be used for binding the identity with the device |
| GetToken | [GetTokenReq](#edgeagentapis-v1-GetTokenReq) | [GetTokenRes](#edgeagentapis-v1-GetTokenRes) | GetToken to receive required token from Scurid Platform App Needed in order to access APIs that need authentication from the Scurid Platform App Not used for authentication locally on the Scurid Edge Agent Also used for refreshing the token |
| DownloadFiles | [DownloadFilesReq](#edgeagentapis-v1-DownloadFilesReq) | [DownloadFilesRes](#edgeagentapis-v1-DownloadFilesRes) | Used for downloading one or more files number of files to download will depend on files prepared by the admin on Scurid Platform App |

 



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


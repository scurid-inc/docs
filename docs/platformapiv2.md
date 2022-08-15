### DeviceContext
Device context from the device in relation to the device identity
#### Reference file : deviceContext.proto

| Field        | Type                                    | Label    | Description                                                                              |
|--------------|-----------------------------------------|----------|------------------------------------------------------------------------------------------|
| macAddresses | [MacAddress](#deviceContext-MacAddress) | repeated | optional, all MAC addresses available to be picked up by the agent                       |
| ipAddress    | [string](#string)                       |          | optional, IP address                                                                     |
| cpu          | [string](#string)                       |          | optional, number of CPUs available                                                       |
| ram          | [string](#string)                       |          | optional, RAM size on the device                                                         |
| imeiNumber   | [string](#string)                       |          | optional, International Mobile Equipment Identity, optional, capture if one is available |
| osType       | [OsInfo](#deviceContext-OsInfo)         |          |                                                                                          |



<a name="deviceContext-MacAddress"></a>

### MacAddress
list of macAddresses from the devices


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| mtu | [int32](#int32) |  | optional, maximum transmission unit |
| macAddress | [string](#string) |  | optional |
| name | [string](#string) |  | interface&#39;s name e.g. en0 |


<a name="deviceContext-OsInfo"></a>

### OsInfo
OsInfo message structure defining standard OS info used within the system


| Field  | Type              | Label | Description                          |
|--------|-------------------|-------|--------------------------------------|
| osType | [string](#string) |       | optional, e.g. darwin, windows, etc. |
| arch   | [string](#string) |       | optional, e.g. amd64 etc.            |


## Platform API v2

#### Reference file : platformapiv2.proto

<a name="platform-v2-AgentsStruct"></a>

### AgentsStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentVersion | [string](#string) |  | version of the Scurid Edge Agent |
| requestedOn | [int64](#int64) |  | date on which Scurid backend received agent&#39;s req for reg. |
| deviceContext | [deviceContext.DeviceContext](#deviceContext-DeviceContext) |  | DeviceContext from the hardware on which the agent is running |
| SignatureOnDeviceContext | [bytes](#bytes) |  | hashed value generated on structure DeviceContext &#43; Requested on &#43; ApprovedOn. THIS is also used as the key which will be delivered to |
| status | [string](#string) |  | current status of the Agent, refer to models/v1/status.go |
| name | [string](#string) |  | alias defined for the agent by the user, if none create one for the user |
| revokedOn | [int64](#int64) |  | RevokedOn timestamp for agent&#39;s identity revocation |
| devices | [string](#string) | repeated | this is the list of identities linked to this agent |
| approvedOn | [int64](#int64) |  | Unix time stamp on which agent&#39;s approved. If client does not provide this, server timestamp will be attached. |
| agentIdentity | [string](#string) |  | agent&#39;s identity |
| platformIdentity | [string](#string) |  | platform&#39;s identity |
| approvalKey | [bytes](#bytes) |  | post approval this key is returned to the agent for reference DeviceContext &#43; Requested on &#43; ApprovedOn &#43; Agent&#39;s DID. THIS is also used as the key which will be delivered to |
| verifiedOn | [int64](#int64) |  | Unix timestamp for verification |



<a name="platform-v2-GetAgentInfoReq"></a>

### GetAgentInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentId | [string](#string) |  | agent&#39;s DID information |






<a name="platform-v2-GetAgentInfoRes"></a>

### GetAgentInfoRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentInfo | [AgentsStruct](#platform-v2-AgentsStruct) |  | uses defined AgentsStruct |






<a name="platform-v2-GetAgentsListReq"></a>

### GetAgentsListReq
GetAgentsListReq

intentionally left empty






<a name="platform-v2-GetAgentsListRes"></a>

### GetAgentsListRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| list | [AgentsStruct](#platform-v2-AgentsStruct) | repeated | array of all the agents along with their details |






<a name="platform-v2-GetAppLogsReq"></a>

### GetAppLogsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| range | [log.LogRange](#log-LogRange) |  |  |






<a name="platform-v2-GetAppLogsRes"></a>

### GetAppLogsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| log | [log.AppLog](#log-AppLog) |  | returns log structure |






<a name="platform-v2-GetIDSettingsReq"></a>

### GetIDSettingsReq
left empty intentionally






<a name="platform-v2-GetIDSettingsRes"></a>

### GetIDSettingsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| autoApproveDeviceID | [bool](#bool) |  | if enabled, new incoming device identities (which usually end up in pending) belonging to existing approved and valid agents will be automatically approved; default is false |






<a name="platform-v2-GetIdentityInfoReq"></a>

### GetIdentityInfoReq
request message for GetIdentityInfo


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  | identity in the format did:scurid:&lt;publicKey&gt; |






<a name="platform-v2-GetIdentityInfoRes"></a>

### GetIdentityInfoRes
response message for GetIdentityInfo


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| vInfo | [string](#string) |  | edge agent version used for creating DID |
| lastVerifiedOn | [int64](#int64) |  | Unix timestamp when an identity was last verified with the SSI Service |
| createdOn | [int64](#int64) |  | Unix timestamp when identity was created |
| rejectedOn | [int64](#int64) |  | Unix timestamp when identity was rejected |
| deviceName | [string](#string) |  | alias name for the device, defined by the user or system |
| isLocal | [bool](#bool) |  | if checked identities are not registered on DLT but only local database |
| path | [string](#string) |  | device pkg file store for staging client files |
| tags | [string](#string) | repeated | provides list of tags attached the identity |
| pendingSince | [int64](#int64) |  | Unix timestamp since identity has been pending for action |
| deviceContext | [deviceContext.DeviceContext](#deviceContext-DeviceContext) |  | helps to onboard and bind a device to an identity |






<a name="platform-v2-GetIdentityLogReq"></a>

### GetIdentityLogReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| range | [log.LogRange](#log-LogRange) |  |  |






<a name="platform-v2-GetIdentityLogRes"></a>

### GetIdentityLogRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| log | [log.IdentityLog](#log-IdentityLog) |  |  |






<a name="platform-v2-RecordAppLogsReq"></a>

### RecordAppLogsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| log | [log.AppLog](#log-AppLog) |  | app log structure |






<a name="platform-v2-RecordAppLogsRes"></a>

### RecordAppLogsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| res | [bool](#bool) |  |  |






<a name="platform-v2-RegisterAgentReq"></a>

### RegisterAgentReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentDID | [string](#string) |  | this is the identity of the agent, auto generated |
| platformDID | [string](#string) |  | this is the platform&#39;s identity generated once during user onboarding |
| name | [string](#string) |  | optional, an alias for the agent |
| approvedOn | [int64](#int64) |  | Unix timestamp, if client won&#39;t send any server will assign current timestamp |






<a name="platform-v2-RegisterAgentRes"></a>

### RegisterAgentRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | true if operation is successful, else false along with error if any |






<a name="platform-v2-RevokeAgentReq"></a>

### RevokeAgentReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentDID | [string](#string) |  | this is the identity of the agent, auto generated |
| platformDID | [string](#string) |  | this is the platform&#39;s identity generated once during user onboarding |
| name | [string](#string) |  | optional, an alias for the agent |
| revokedOn | [int64](#int64) |  | Unix timestamp, if client won&#39;t send any server will assign current timestamp |






<a name="platform-v2-RevokeAgentRes"></a>

### RevokeAgentRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | true if operation is successful, else false along with error if any |






<a name="platform-v2-SetIDSettingsReq"></a>

### SetIDSettingsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| autoApproveDeviceID | [bool](#bool) |  | if enabled, new incoming device identities (which usually end up in pending) belonging to existing approved and valid agents will be automatically approved; default is false |






<a name="platform-v2-SetIDSettingsRes"></a>

### SetIDSettingsRes
SetIDSettingsRes is the response from the backend


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | returns true if successful |






<a name="platform-v2-VerifyAgentReq"></a>

### VerifyAgentReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentDID | [string](#string) |  | this is the identity of the agent, auto generated |
| platformDID | [string](#string) |  | this is the platform&#39;s identity generated once during user onboarding |






<a name="platform-v2-VerifyAgentRes"></a>

### VerifyAgentRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | true if status is still approved , else false along with error if any |












<a name="platform-v2-Platform"></a>

### Platform


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetIdentityInfo | [GetIdentityInfoReq](#platform-v2-GetIdentityInfoReq) | [GetIdentityInfoRes](#platform-v2-GetIdentityInfoRes) | Fetches details available on a given identity in local DB storage it can be used for any kind of identity i.e.approved, rejected or pending GetIdentityInfo is currently under development do not use // |
| GetAgentsList | [GetAgentsListReq](#platform-v2-GetAgentsListReq) | [GetAgentsListRes](#platform-v2-GetAgentsListRes) | GetAgentsList returns list of all agents along with their details |
| GetAgentInfo | [GetAgentInfoReq](#platform-v2-GetAgentInfoReq) | [GetAgentInfoRes](#platform-v2-GetAgentInfoRes) | GetAgentInfo returns detail about individual agent identity |
| RegisterAgent | [RegisterAgentReq](#platform-v2-RegisterAgentReq) | [RegisterAgentRes](#platform-v2-RegisterAgentRes) | RegisterAgent approves a pending agent in the system |
| RevokeAgent | [RevokeAgentReq](#platform-v2-RevokeAgentReq) | [RevokeAgentRes](#platform-v2-RevokeAgentRes) | RevokeAgent revokes an agent&#39;s identity |
| VerifyAgent | [VerifyAgentReq](#platform-v2-VerifyAgentReq) | [VerifyAgentRes](#platform-v2-VerifyAgentRes) | VerifyAgent verifies agent&#39;s authenticity against the Scurid SSI service |


<a name="platform-v2-Subsystems"></a>

### Subsystems
Provides configuration possibilities for different components in the system

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetIDSettings | [GetIDSettingsReq](#platform-v2-GetIDSettingsReq) | [GetIDSettingsRes](#platform-v2-GetIDSettingsRes) | GetIDSettings gets currently stored settings about IDs |
| SetIDSettings | [SetIDSettingsReq](#platform-v2-SetIDSettingsReq) | [SetIDSettingsRes](#platform-v2-SetIDSettingsRes) | SetIDSettings sets up different settings |
| GetIdentityLog | [GetIdentityLogReq](#platform-v2-GetIdentityLogReq) | [GetIdentityLogRes](#platform-v2-GetIdentityLogRes) stream | GetIdentityLog provides list of log recorded on activities performed on identities. This covers both agent and non agent identities. |
| RecordAppLogs | [RecordAppLogsReq](#platform-v2-RecordAppLogsReq) | [RecordAppLogsRes](#platform-v2-RecordAppLogsRes) | RecordAppLogs records Scurid App logs |
| GetAppLogs | [GetAppLogsReq](#platform-v2-GetAppLogsReq) | [GetAppLogsRes](#platform-v2-GetAppLogsRes) stream | GetAppLogs fetches app log persisted as history |





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


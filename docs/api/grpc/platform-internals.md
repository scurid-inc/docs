# Platform Internal APIs Documentation
<a name="top"></a>

## Table of Contents

- [platformInternal.proto](#platformInternal-proto)
    - [CloudProviders](#platformInternal-CloudProviders)
    - [CreateCredentialsReq](#platformInternal-CreateCredentialsReq)
    - [CreateCredentialsRes](#platformInternal-CreateCredentialsRes)
    - [DataStoreRegion](#platformInternal-DataStoreRegion)
    - [DataStoreRegionForAgent](#platformInternal-DataStoreRegionForAgent)
    - [DatabaseCredential](#platformInternal-DatabaseCredential)
    - [GetAgentConfigReq](#platformInternal-GetAgentConfigReq)
    - [GetAgentConfigRes](#platformInternal-GetAgentConfigRes)
    - [GetAgentRegionConfigReq](#platformInternal-GetAgentRegionConfigReq)
    - [GetAgentRegionConfigRes](#platformInternal-GetAgentRegionConfigRes)
    - [GetCloudProvidersReq](#platformInternal-GetCloudProvidersReq)
    - [GetCloudProvidersRes](#platformInternal-GetCloudProvidersRes)
    - [GetCredentialsReq](#platformInternal-GetCredentialsReq)
    - [GetCredentialsRes](#platformInternal-GetCredentialsRes)
    - [GetDBRegionListReq](#platformInternal-GetDBRegionListReq)
    - [GetDBRegionListRes](#platformInternal-GetDBRegionListRes)
    - [GetUserRegionConfigReq](#platformInternal-GetUserRegionConfigReq)
    - [GetUserRegionConfigRes](#platformInternal-GetUserRegionConfigRes)
    - [OtherPlatformIntegrationReq](#platformInternal-OtherPlatformIntegrationReq)
    - [OtherPlatformIntegrationRes](#platformInternal-OtherPlatformIntegrationRes)
    - [RegionConfigForAgent](#platformInternal-RegionConfigForAgent)
    - [RequestAgentRegistrationReq](#platformInternal-RequestAgentRegistrationReq)
    - [RequestAgentRegistrationRes](#platformInternal-RequestAgentRegistrationRes)
    - [SendReq](#platformInternal-SendReq)
    - [SendRes](#platformInternal-SendRes)
    - [SendWithUserDefinedFieldsReq](#platformInternal-SendWithUserDefinedFieldsReq)
    - [SendWithUserDefinedFieldsRes](#platformInternal-SendWithUserDefinedFieldsRes)
    - [StatusCheckReq](#platformInternal-StatusCheckReq)
    - [StatusCheckRes](#platformInternal-StatusCheckRes)
    - [StoreAgentRegionConfigReq](#platformInternal-StoreAgentRegionConfigReq)
    - [StoreAgentRegionConfigRes](#platformInternal-StoreAgentRegionConfigRes)
    - [StoreRegionConfigReq](#platformInternal-StoreRegionConfigReq)
    - [StoreRegionConfigRes](#platformInternal-StoreRegionConfigRes)
    - [ThingWorx](#platformInternal-ThingWorx)
  
    - [AgentManagement](#platformInternal-AgentManagement)
    - [CustomSender](#platformInternal-CustomSender)
    - [DataStorage](#platformInternal-DataStorage)
    - [DeviceDataManagement](#platformInternal-DeviceDataManagement)
  
- [Scalar Value Types](#scalar-value-types)



<a name="platformInternal-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## platformInternal.proto



<a name="platformInternal-CloudProviders"></a>

### CloudProviders



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  | e.g. AWS, GCP, Azure etc. |






<a name="platformInternal-CreateCredentialsReq"></a>

### CreateCredentialsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| credential | [DatabaseCredential](#platformInternal-DatabaseCredential) |  |  |
| dataStoreRegionId | [int64](#int64) |  | this is the internal id assigned by Scurid; it must be available to create an identity. Call GetUserRegionConfig to get the id if not available. |






<a name="platformInternal-CreateCredentialsRes"></a>

### CreateCredentialsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| res | [bool](#bool) |  |  |






<a name="platformInternal-DataStoreRegion"></a>

### DataStoreRegion



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| regionName | [string](#string) |  | e.g. west-eu-1, japan-east-1, names returned here must match the naming conventions from the cloud |
| id | [int64](#int64) |  | this is the internal id assigned by Scurid |
| gps | [string](#string) |  | this is the gps location of the datacenter provided by the cloud provider |
| enabled | [bool](#bool) |  | default is false, if region&#39;s available true is returned |
| regionGroup | [string](#string) |  | e.g. EMEA, APAC, US, etc. |
| cloudProviderName | [string](#string) |  | e.g. AWS, GCP, Azure etc. |






<a name="platformInternal-DataStoreRegionForAgent"></a>

### DataStoreRegionForAgent
for agents under user / customer


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [DataStoreRegion](#platformInternal-DataStoreRegion) |  | this is the regional and cloud configuration defined by the users |
| platformIdentity | [string](#string) |  | this is the did of the platform |
| isAgentEnabled | [bool](#bool) |  | this provides information if the agent has been enabled by the user for data storage. |






<a name="platformInternal-DatabaseCredential"></a>

### DatabaseCredential



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| username | [string](#string) |  |  |
| password | [string](#string) |  |  |
| databaseName | [string](#string) |  |  |






<a name="platformInternal-GetAgentConfigReq"></a>

### GetAgentConfigReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| AgentID | [string](#string) |  |  |






<a name="platformInternal-GetAgentConfigRes"></a>

### GetAgentConfigRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| integrationDetails | [integration.IntegrationDetails](#integration-IntegrationDetails) |  |  |






<a name="platformInternal-GetAgentRegionConfigReq"></a>

### GetAgentRegionConfigReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentIdentity | [string](#string) |  | this is the agent identity, i.e. the DID, caller can request information on one |






<a name="platformInternal-GetAgentRegionConfigRes"></a>

### GetAgentRegionConfigRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentRegionInfo | [DataStoreRegionForAgent](#platformInternal-DataStoreRegionForAgent) | repeated |  |






<a name="platformInternal-GetCloudProvidersReq"></a>

### GetCloudProvidersReq
intentionally left empty






<a name="platformInternal-GetCloudProvidersRes"></a>

### GetCloudProvidersRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| providers | [CloudProviders](#platformInternal-CloudProviders) | repeated |  |






<a name="platformInternal-GetCredentialsReq"></a>

### GetCredentialsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| platformIdentity | [string](#string) |  |  |






<a name="platformInternal-GetCredentialsRes"></a>

### GetCredentialsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| credentials | [DatabaseCredential](#platformInternal-DatabaseCredential) | repeated |  |






<a name="platformInternal-GetDBRegionListReq"></a>

### GetDBRegionListReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| cloudProviderName | [string](#string) |  | this the name of the |






<a name="platformInternal-GetDBRegionListRes"></a>

### GetDBRegionListRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| regionInfo | [DataStoreRegion](#platformInternal-DataStoreRegion) |  |  |






<a name="platformInternal-GetUserRegionConfigReq"></a>

### GetUserRegionConfigReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| platformIdentity | [string](#string) |  | this is the platform DID of the user |






<a name="platformInternal-GetUserRegionConfigRes"></a>

### GetUserRegionConfigRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| userCreatedRegions | [DataStoreRegion](#platformInternal-DataStoreRegion) | repeated |  |






<a name="platformInternal-OtherPlatformIntegrationReq"></a>

### OtherPlatformIntegrationReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| thingWorx | [ThingWorx](#platformInternal-ThingWorx) |  | config. related to ThingWorx |






<a name="platformInternal-OtherPlatformIntegrationRes"></a>

### OtherPlatformIntegrationRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| thingWorx | [ThingWorx](#platformInternal-ThingWorx) |  |  |






<a name="platformInternal-RegionConfigForAgent"></a>

### RegionConfigForAgent



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentIdentity | [string](#string) |  | this is the DID of the agent |
| regionConfigId | [int64](#int64) |  | this MUST be acquired by calling GetUserRegionConfig. The regions used for storing the information for the agent must already have been created in the system |






<a name="platformInternal-RequestAgentRegistrationReq"></a>

### RequestAgentRegistrationReq
response message for RequestAgentRegistration


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentVerInfo | [string](#string) |  | edge agent version used for creating DID |
| requestedOn | [int64](#int64) |  | Unix timestamp when identity was created |
| deviceContext | [deviceContext.DeviceContext](#deviceContext-DeviceContext) |  | helps to onboard and bind a device to an identity |
| signatureOnDeviceContext | [bytes](#bytes) |  | hash calculated on the fields requestedOn &#43; DeviceContext. THIS must be sent by the agent and will be recorded on the backend and used for future verification. |
| agentDID | [string](#string) |  | this is the DID of the agent |






<a name="platformInternal-RequestAgentRegistrationRes"></a>

### RequestAgentRegistrationRes
RequestAgentRegistrationRes is the response from RequestAgentRegistration


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | True if successfully completed the requested of registration else false. |






<a name="platformInternal-SendReq"></a>

### SendReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentDID | [string](#string) |  |  |
| mawaData | [deviceData.MaWaRouteDataStruct](#deviceData-MaWaRouteDataStruct) |  | specific to MaWaRoute |
| deviceData | [deviceData.DeviceData](#deviceData-DeviceData) |  | this is the generic structure for users deploying Scurid Edge Agent and using its data transfer capabilities. This is could JSON string for now. Need more work to create more customer specific structure |
| csr | [certificate.v1.CSR](#certificate-v1-CSR) |  |  |






<a name="platformInternal-SendRes"></a>

### SendRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| res | [bool](#bool) |  |  |






<a name="platformInternal-SendWithUserDefinedFieldsReq"></a>

### SendWithUserDefinedFieldsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| row | [string](#string) |  |  |
| signature | [string](#string) |  |  |
| timestamp | [int64](#int64) |  |  |
| agentDID | [string](#string) |  |  |






<a name="platformInternal-SendWithUserDefinedFieldsRes"></a>

### SendWithUserDefinedFieldsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| success | [bool](#bool) |  |  |






<a name="platformInternal-StatusCheckReq"></a>

### StatusCheckReq
StatusCheckReq used for checking the agent status


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentDID | [string](#string) |  | this is the DID of the agent |






<a name="platformInternal-StatusCheckRes"></a>

### StatusCheckRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  | this is the key returned by the backend, that must be used by the identities to relate themselves to an agent |
| status | [string](#string) |  | to enable decision making on the edge agent |
| otherPlatformIntegrationRes | [OtherPlatformIntegrationRes](#platformInternal-OtherPlatformIntegrationRes) |  |  |






<a name="platformInternal-StoreAgentRegionConfigReq"></a>

### StoreAgentRegionConfigReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [RegionConfigForAgent](#platformInternal-RegionConfigForAgent) |  | data to store the information for agent&#39;s config |
| enableStorage | [bool](#bool) |  | this controls if the agent should use the config to write to the datastore |






<a name="platformInternal-StoreAgentRegionConfigRes"></a>

### StoreAgentRegionConfigRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  | default is false, when stores successfully true is returned |






<a name="platformInternal-StoreRegionConfigReq"></a>

### StoreRegionConfigReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| identity | [string](#string) |  | use the platformDID |
| id | [int64](#int64) |  | use the value defined from the DataStoreRegion.ID |






<a name="platformInternal-StoreRegionConfigRes"></a>

### StoreRegionConfigRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  | default is false, if successful True is returned |






<a name="platformInternal-ThingWorx"></a>

### ThingWorx



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| RequestOnboard | [bool](#bool) |  |  |
| AppKey | [string](#string) |  |  |





 

 

 


<a name="platformInternal-AgentManagement"></a>

### AgentManagement
AgentManagement contains endpoint that are needed to manage internal communication between the Agents and the Platform
This will be used to perform internal tasks, that can be offload from users to simplify agent to platform workings

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| RequestAgentRegistration | [RequestAgentRegistrationReq](#platformInternal-RequestAgentRegistrationReq) | [RequestAgentRegistrationRes](#platformInternal-RequestAgentRegistrationRes) | Requests the registration of an agent |
| StatusCheck | [StatusCheckReq](#platformInternal-StatusCheckReq) | [StatusCheckRes](#platformInternal-StatusCheckRes) | StatusCheck provides update if the identity for the agent is approved if approved agent will receive a key |
| GetAgentConfig | [GetAgentConfigReq](#platformInternal-GetAgentConfigReq) | [GetAgentConfigRes](#platformInternal-GetAgentConfigRes) |  |


<a name="platformInternal-CustomSender"></a>

### CustomSender


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| SendWithUserDefinedFields | [SendWithUserDefinedFieldsReq](#platformInternal-SendWithUserDefinedFieldsReq) stream | [SendWithUserDefinedFieldsRes](#platformInternal-SendWithUserDefinedFieldsRes) |  |


<a name="platformInternal-DataStorage"></a>

### DataStorage
Allows setting up global database store for the Scurid Backend which enables Scurid Edge agents to store device data

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetCloudProviders | [GetCloudProvidersReq](#platformInternal-GetCloudProvidersReq) | [GetCloudProvidersRes](#platformInternal-GetCloudProvidersRes) | GetCloudProviders fetches list of currently supported cloud providers this API is to deliver default configuration offered by Scurid |
| GetDBRegionList | [GetDBRegionListReq](#platformInternal-GetDBRegionListReq) | [GetDBRegionListRes](#platformInternal-GetDBRegionListRes) stream | GetDBRegionList provides list of global region list where distributed data storage can be setup this API is to deliver default configuration offered by Scurid |
| StoreRegionConfig | [StoreRegionConfigReq](#platformInternal-StoreRegionConfigReq) | [StoreRegionConfigRes](#platformInternal-StoreRegionConfigRes) | StoreRegionConfig stores region information as selected by the user this helps build region configuration for the end users |
| GetUserRegionConfig | [GetUserRegionConfigReq](#platformInternal-GetUserRegionConfigReq) | [GetUserRegionConfigRes](#platformInternal-GetUserRegionConfigRes) | GetUserRegionConfig fetches list of regions configured for the user this API must be used after the initial on-boarding is finished using StoreRegionConfig this helps build region configuration for the end user scope |
| StoreAgentRegionConfig | [StoreAgentRegionConfigReq](#platformInternal-StoreAgentRegionConfigReq) | [StoreAgentRegionConfigRes](#platformInternal-StoreAgentRegionConfigRes) | StoreAgentRegionConfig stores agent&#39;s region configuration this API must be used after the initial user region setup is complete via StoreRegionConfig |
| GetAgentRegionConfig | [GetAgentRegionConfigReq](#platformInternal-GetAgentRegionConfigReq) | [GetAgentRegionConfigRes](#platformInternal-GetAgentRegionConfigRes) | GetAgentRegionConfig fetches list of region configuration for the agent this API must be used after the initial agent setup is complete via StoreAgentRegionConfig |
| CreateCredentials | [CreateCredentialsReq](#platformInternal-CreateCredentialsReq) | [CreateCredentialsRes](#platformInternal-CreateCredentialsRes) | CreateCredentials create required username , password, connection string and the database name for the user |
| GetCredentials | [GetCredentialsReq](#platformInternal-GetCredentialsReq) | [GetCredentialsRes](#platformInternal-GetCredentialsRes) | Fetches the credentials for a given customer |
| GetAgentData | [.deviceData.GetAgentDataReq](#deviceData-GetAgentDataReq) | [.deviceData.GetAgentDataRes](#deviceData-GetAgentDataRes) stream | GetDevicesList returns list of all agent data |
| GetAgentDataStat | [.deviceData.GetAgentDataStatReq](#deviceData-GetAgentDataStatReq) | [.deviceData.GetAgentDataStatRes](#deviceData-GetAgentDataStatRes) | GetAgentDataStat returns the number of data that can be successfully verified and dataPoints that couldn&#39;t be verified |


<a name="platformInternal-DeviceDataManagement"></a>

### DeviceDataManagement
DeviceDataManagement set of endpoints to help manage data flow from devices back to Scurid Backend

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Send | [SendReq](#platformInternal-SendReq) stream | [SendRes](#platformInternal-SendRes) stream | Send opens bidi stream, between device and the server currently server is only configured to return boolean confirmation. todo extend for more later. |
| SendWithUserDefinedFields | [SendWithUserDefinedFieldsReq](#platformInternal-SendWithUserDefinedFieldsReq) stream | [SendWithUserDefinedFieldsRes](#platformInternal-SendWithUserDefinedFieldsRes) | SendWithUserDefinedFields creates client streaming to send array of data set from the Scurid Edge Agent to the Scurid Server |

 



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


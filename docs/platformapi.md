# Platform API Documentation
<a name="top"></a>

## Table of Contents

- [deviceContext.proto](#deviceContext-proto)
    - [DeviceContext](#deviceContext-DeviceContext)
    - [MacAddress](#deviceContext-MacAddress)
    - [OsInfo](#deviceContext-OsInfo)
  
- [platformapi.proto](#platformapi-proto)
    - [AddTagsReq](#scuridplatformagentapi-v1-AddTagsReq)
    - [AddTagsRes](#scuridplatformagentapi-v1-AddTagsRes)
    - [AgentInfoForDID](#scuridplatformagentapi-v1-AgentInfoForDID)
    - [AllDevicesListStruct](#scuridplatformagentapi-v1-AllDevicesListStruct)
    - [AssignTagsToIdentityReq](#scuridplatformagentapi-v1-AssignTagsToIdentityReq)
    - [AssignTagsToIdentityRes](#scuridplatformagentapi-v1-AssignTagsToIdentityRes)
    - [CountriesStruct](#scuridplatformagentapi-v1-CountriesStruct)
    - [CreateIdentityReq](#scuridplatformagentapi-v1-CreateIdentityReq)
    - [CreateIdentityRes](#scuridplatformagentapi-v1-CreateIdentityRes)
    - [DownloadFilesReq](#scuridplatformagentapi-v1-DownloadFilesReq)
    - [DownloadFilesRes](#scuridplatformagentapi-v1-DownloadFilesRes)
    - [EmptyRequest](#scuridplatformagentapi-v1-EmptyRequest)
    - [FileInfo](#scuridplatformagentapi-v1-FileInfo)
    - [FileStorePathReq](#scuridplatformagentapi-v1-FileStorePathReq)
    - [FileStorePathRes](#scuridplatformagentapi-v1-FileStorePathRes)
    - [GetAllDevicesListReq](#scuridplatformagentapi-v1-GetAllDevicesListReq)
    - [GetAllDevicesListRes](#scuridplatformagentapi-v1-GetAllDevicesListRes)
    - [GetCountriesListReq](#scuridplatformagentapi-v1-GetCountriesListReq)
    - [GetCountriesListRes](#scuridplatformagentapi-v1-GetCountriesListRes)
    - [GetDevicePayloadsWithSignatureReq](#scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureReq)
    - [GetDevicePayloadsWithSignatureRes](#scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureRes)
    - [GetDevicePayloadsWithSignatureStruct](#scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureStruct)
    - [GetLicenseStatusReq](#scuridplatformagentapi-v1-GetLicenseStatusReq)
    - [GetLicenseStatusRes](#scuridplatformagentapi-v1-GetLicenseStatusRes)
    - [GetOnboardingPkgReq](#scuridplatformagentapi-v1-GetOnboardingPkgReq)
    - [GetOnboardingPkgRes](#scuridplatformagentapi-v1-GetOnboardingPkgRes)
    - [GetPendingRequestsListReq](#scuridplatformagentapi-v1-GetPendingRequestsListReq)
    - [GetPendingRequestsListRes](#scuridplatformagentapi-v1-GetPendingRequestsListRes)
    - [GetPlatformDIDReq](#scuridplatformagentapi-v1-GetPlatformDIDReq)
    - [GetPlatformDIDRes](#scuridplatformagentapi-v1-GetPlatformDIDRes)
    - [GetRejectedIdentitiesListReq](#scuridplatformagentapi-v1-GetRejectedIdentitiesListReq)
    - [GetRejectedIdentitiesListRes](#scuridplatformagentapi-v1-GetRejectedIdentitiesListRes)
    - [GetTagsReq](#scuridplatformagentapi-v1-GetTagsReq)
    - [GetTagsRes](#scuridplatformagentapi-v1-GetTagsRes)
    - [GetValidIdentitiesListReq](#scuridplatformagentapi-v1-GetValidIdentitiesListReq)
    - [GetValidIdentitiesListRes](#scuridplatformagentapi-v1-GetValidIdentitiesListRes)
    - [GetValidIdentityInfoReq](#scuridplatformagentapi-v1-GetValidIdentityInfoReq)
    - [GetValidIdentityInfoRes](#scuridplatformagentapi-v1-GetValidIdentityInfoRes)
    - [ListIdentitiesUnderATagReq](#scuridplatformagentapi-v1-ListIdentitiesUnderATagReq)
    - [ListIdentitiesUnderATagRes](#scuridplatformagentapi-v1-ListIdentitiesUnderATagRes)
    - [LocalStorageInitReq](#scuridplatformagentapi-v1-LocalStorageInitReq)
    - [LocalStorageInitRes](#scuridplatformagentapi-v1-LocalStorageInitRes)
    - [NewPlatformUserInfo](#scuridplatformagentapi-v1-NewPlatformUserInfo)
    - [PendingRequestsStruct](#scuridplatformagentapi-v1-PendingRequestsStruct)
    - [PostDeviceDataWithSignatureReq](#scuridplatformagentapi-v1-PostDeviceDataWithSignatureReq)
    - [PostDeviceDataWithSignatureRes](#scuridplatformagentapi-v1-PostDeviceDataWithSignatureRes)
    - [PostDeviceDataWithSignatureStruct](#scuridplatformagentapi-v1-PostDeviceDataWithSignatureStruct)
    - [RecordRejectedDIDReq](#scuridplatformagentapi-v1-RecordRejectedDIDReq)
    - [RecordRejectedDIDRes](#scuridplatformagentapi-v1-RecordRejectedDIDRes)
    - [RegisterDeviceDIDReq](#scuridplatformagentapi-v1-RegisterDeviceDIDReq)
    - [RegisterDeviceDIDRes](#scuridplatformagentapi-v1-RegisterDeviceDIDRes)
    - [RejectedIdentitiesListStruct](#scuridplatformagentapi-v1-RejectedIdentitiesListStruct)
    - [RemoveTagsReq](#scuridplatformagentapi-v1-RemoveTagsReq)
    - [RemoveTagsRes](#scuridplatformagentapi-v1-RemoveTagsRes)
    - [RequestIdentityStatusReq](#scuridplatformagentapi-v1-RequestIdentityStatusReq)
    - [RequestIdentityStatusRes](#scuridplatformagentapi-v1-RequestIdentityStatusRes)
    - [RequestRegistrationOfDeviceReq](#scuridplatformagentapi-v1-RequestRegistrationOfDeviceReq)
    - [RequestRegistrationOfDeviceRes](#scuridplatformagentapi-v1-RequestRegistrationOfDeviceRes)
    - [RevokeDeviceDIDReq](#scuridplatformagentapi-v1-RevokeDeviceDIDReq)
    - [RevokeDeviceDIDRes](#scuridplatformagentapi-v1-RevokeDeviceDIDRes)
    - [SignBytePayloadWithIdentityReq](#scuridplatformagentapi-v1-SignBytePayloadWithIdentityReq)
    - [SignBytePayloadWithIdentityRes](#scuridplatformagentapi-v1-SignBytePayloadWithIdentityRes)
    - [SignPayloadReq](#scuridplatformagentapi-v1-SignPayloadReq)
    - [SignPayloadRes](#scuridplatformagentapi-v1-SignPayloadRes)
    - [TagStruct](#scuridplatformagentapi-v1-TagStruct)
    - [UploadFilesReq](#scuridplatformagentapi-v1-UploadFilesReq)
    - [UploadFilesRes](#scuridplatformagentapi-v1-UploadFilesRes)
    - [ValidIdentitiesListStruct](#scuridplatformagentapi-v1-ValidIdentitiesListStruct)
    - [VerifyBytePayloadWithIdentityReq](#scuridplatformagentapi-v1-VerifyBytePayloadWithIdentityReq)
    - [VerifyBytePayloadWithIdentityRes](#scuridplatformagentapi-v1-VerifyBytePayloadWithIdentityRes)
    - [VerifyDeviceDIDReq](#scuridplatformagentapi-v1-VerifyDeviceDIDReq)
    - [VerifyDeviceDIDRes](#scuridplatformagentapi-v1-VerifyDeviceDIDRes)
    - [VerifySignatureReq](#scuridplatformagentapi-v1-VerifySignatureReq)
    - [VerifySignatureRes](#scuridplatformagentapi-v1-VerifySignatureRes)
  
    - [ScuridServerAPI](#scuridplatformagentapi-v1-ScuridPlatformAgentAPI)
  
- [Scalar Value Types](#scalar-value-types)



<a name="deviceContext-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## deviceContext.proto



<a name="deviceContext-DeviceContext"></a>

### DeviceContext
Device context from the device in relation to the device identity


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| macAddresses | [MacAddress](#deviceContext-MacAddress) | repeated | optional, all MAC addresses available to be picked up by the agent |
| ipAddress | [string](#string) |  | optional, IP address |
| cpu | [string](#string) |  | optional, number of CPUs available |
| ram | [string](#string) |  | optional, RAM size on the device |
| imeiNumber | [string](#string) |  | optional, International Mobile Equipment Identity, optional, capture if one is available |
| osType | [OsInfo](#deviceContext-OsInfo) |  |  |






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


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| osType | [string](#string) |  | optional, e.g. darwin, windows, etc. |
| arch | [string](#string) |  | optional, e.g. amd64 etc. |





 

 

 

 



<a name="platformapi-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## platformapi.proto



<a name="scuridplatformagentapi-v1-AddTagsReq"></a>

### AddTagsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tags | [TagStruct](#scuridplatformagentapi-v1-TagStruct) | repeated | one or more tags to be created in the system |






<a name="scuridplatformagentapi-v1-AddTagsRes"></a>

### AddTagsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | boolean result, True if all gets created else false |






<a name="scuridplatformagentapi-v1-AgentInfoForDID"></a>

### AgentInfoForDID



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentDID | [string](#string) |  | if device DID to be bound to an agent |
| statusKey | [string](#string) |  | to be delivered from the backend |






<a name="scuridplatformagentapi-v1-AllDevicesListStruct"></a>

### AllDevicesListStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |
| deviceName | [string](#string) |  | human readable name of the device |
| statusOfDID | [string](#string) |  |  |
| versionInfo | [string](#string) |  |  |
| createdOn | [int64](#int64) |  |  |






<a name="scuridplatformagentapi-v1-AssignTagsToIdentityReq"></a>

### AssignTagsToIdentityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tags | [TagStruct](#scuridplatformagentapi-v1-TagStruct) | repeated |  |
| did | [string](#string) |  | device identities to be tagged with |






<a name="scuridplatformagentapi-v1-AssignTagsToIdentityRes"></a>

### AssignTagsToIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | true if assignment of tags to identity works; else false; default is false |






<a name="scuridplatformagentapi-v1-CountriesStruct"></a>

### CountriesStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-CreateIdentityReq"></a>

### CreateIdentityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| customerInfo | [NewPlatformUserInfo](#scuridplatformagentapi-v1-NewPlatformUserInfo) |  |  |






<a name="scuridplatformagentapi-v1-CreateIdentityRes"></a>

### CreateIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-DownloadFilesReq"></a>

### DownloadFilesReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceIdentity | [string](#string) |  | device&#39;s identity |






<a name="scuridplatformagentapi-v1-DownloadFilesRes"></a>

### DownloadFilesRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| info | [FileInfo](#scuridplatformagentapi-v1-FileInfo) |  |  |
| chunkData | [bytes](#bytes) |  |  |






<a name="scuridplatformagentapi-v1-EmptyRequest"></a>

### EmptyRequest







<a name="scuridplatformagentapi-v1-FileInfo"></a>

### FileInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceIdentity | [string](#string) |  |  |
| fileId | [string](#string) |  |  |
| fileType | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-FileStorePathReq"></a>

### FileStorePathReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceIdentity | [string](#string) |  | device DID |
| path | [string](#string) |  | folder |






<a name="scuridplatformagentapi-v1-FileStorePathRes"></a>

### FileStorePathRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  |  |






<a name="scuridplatformagentapi-v1-GetAllDevicesListReq"></a>

### GetAllDevicesListReq
empty request






<a name="scuridplatformagentapi-v1-GetAllDevicesListRes"></a>

### GetAllDevicesListRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rows | [AllDevicesListStruct](#scuridplatformagentapi-v1-AllDevicesListStruct) | repeated |  |






<a name="scuridplatformagentapi-v1-GetCountriesListReq"></a>

### GetCountriesListReq
left blank intentionally






<a name="scuridplatformagentapi-v1-GetCountriesListRes"></a>

### GetCountriesListRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [CountriesStruct](#scuridplatformagentapi-v1-CountriesStruct) | repeated |  |






<a name="scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureReq"></a>

### GetDevicePayloadsWithSignatureReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceDid | [string](#string) |  |  |
| deviceName | [string](#string) |  | if deviceName is used all payloads are returned from that device, it may have used multiple DIDs |






<a name="scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureRes"></a>

### GetDevicePayloadsWithSignatureRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rows | [GetDevicePayloadsWithSignatureStruct](#scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureStruct) | repeated |  |






<a name="scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureStruct"></a>

### GetDevicePayloadsWithSignatureStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceDID | [string](#string) |  |  |
| deviceName | [string](#string) |  |  |
| dataTimestamp | [int32](#int32) |  |  |
| payload | [string](#string) |  |  |
| signature | [string](#string) |  |  |
| isValid | [bool](#bool) |  |  |






<a name="scuridplatformagentapi-v1-GetLicenseStatusReq"></a>

### GetLicenseStatusReq
ScuridPlatformAgentAPI section

left blank intentionally






<a name="scuridplatformagentapi-v1-GetLicenseStatusRes"></a>

### GetLicenseStatusRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| licStatus | [bool](#bool) |  | false if status not active; true otherwise |
| licType | [string](#string) |  | type of the license small, developer etc. |
| validFrom | [int64](#int64) |  | valid from timestamp |
| validUntil | [int64](#int64) |  | valid until timestamp |






<a name="scuridplatformagentapi-v1-GetOnboardingPkgReq"></a>

### GetOnboardingPkgReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| identity | [string](#string) |  | device&#39;s public identity |






<a name="scuridplatformagentapi-v1-GetOnboardingPkgRes"></a>

### GetOnboardingPkgRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pkg1 | [string](#string) |  | transfers payload in string, any data structure |
| pkg2 | [bytes](#bytes) |  | transfers payload in bytes, any data structure |






<a name="scuridplatformagentapi-v1-GetPendingRequestsListReq"></a>

### GetPendingRequestsListReq
empty request






<a name="scuridplatformagentapi-v1-GetPendingRequestsListRes"></a>

### GetPendingRequestsListRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rows | [PendingRequestsStruct](#scuridplatformagentapi-v1-PendingRequestsStruct) | repeated |  |






<a name="scuridplatformagentapi-v1-GetPlatformDIDReq"></a>

### GetPlatformDIDReq
empty request






<a name="scuridplatformagentapi-v1-GetPlatformDIDRes"></a>

### GetPlatformDIDRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| platform_did | [string](#string) |  |  |
| status | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-GetRejectedIdentitiesListReq"></a>

### GetRejectedIdentitiesListReq
empty request






<a name="scuridplatformagentapi-v1-GetRejectedIdentitiesListRes"></a>

### GetRejectedIdentitiesListRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rows | [RejectedIdentitiesListStruct](#scuridplatformagentapi-v1-RejectedIdentitiesListStruct) | repeated |  |






<a name="scuridplatformagentapi-v1-GetTagsReq"></a>

### GetTagsReq
left empty






<a name="scuridplatformagentapi-v1-GetTagsRes"></a>

### GetTagsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tag | [TagStruct](#scuridplatformagentapi-v1-TagStruct) |  |  |






<a name="scuridplatformagentapi-v1-GetValidIdentitiesListReq"></a>

### GetValidIdentitiesListReq
empty request






<a name="scuridplatformagentapi-v1-GetValidIdentitiesListRes"></a>

### GetValidIdentitiesListRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rows | [ValidIdentitiesListStruct](#scuridplatformagentapi-v1-ValidIdentitiesListStruct) | repeated |  |






<a name="scuridplatformagentapi-v1-GetValidIdentityInfoReq"></a>

### GetValidIdentityInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-GetValidIdentityInfoRes"></a>

### GetValidIdentityInfoRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| vInfo | [string](#string) |  | edge agent version used for creating DID |
| lastVerifiedOn | [int64](#int64) |  |  |
| created_on | [int64](#int64) |  |  |
| device_name | [string](#string) |  |  |
| isLocal | [bool](#bool) |  | if checked identities are not registered on DLT but only local database |
| path | [string](#string) |  | device pkg file store on the client side |
| deviceContext | [deviceContext.DeviceContext](#deviceContext-DeviceContext) |  | helps to onboard and bind a device to an identity |
| agentInfoForDID | [AgentInfoForDID](#scuridplatformagentapi-v1-AgentInfoForDID) |  | if there is an agent to which this identity belongs |






<a name="scuridplatformagentapi-v1-ListIdentitiesUnderATagReq"></a>

### ListIdentitiesUnderATagReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tag | [TagStruct](#scuridplatformagentapi-v1-TagStruct) |  |  |






<a name="scuridplatformagentapi-v1-ListIdentitiesUnderATagRes"></a>

### ListIdentitiesUnderATagRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-LocalStorageInitReq"></a>

### LocalStorageInitReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| storagePath | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-LocalStorageInitRes"></a>

### LocalStorageInitRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  | try to return actual error from the OS if any, a success message |






<a name="scuridplatformagentapi-v1-NewPlatformUserInfo"></a>

### NewPlatformUserInfo
struct to be attached to the Platform&#39;s DID registration


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| firstName | [string](#string) |  |  |
| lastName | [string](#string) |  |  |
| email | [string](#string) |  |  |
| country | [string](#string) |  |  |
| isEnterpriseUser | [bool](#bool) |  |  |
| enterpriseFullName | [string](#string) |  |  |
| did | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-PendingRequestsStruct"></a>

### PendingRequestsStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |
| requestTimestamp | [int64](#int64) |  |  |
| versionInfo | [string](#string) |  |  |
| created_on | [int64](#int64) |  |  |
| device_name | [string](#string) |  |  |
| isLocal | [bool](#bool) |  |  |
| deviceContext | [deviceContext.DeviceContext](#deviceContext-DeviceContext) |  | helps to onboard and bind a device to an identity |
| agentInfoForDID | [AgentInfoForDID](#scuridplatformagentapi-v1-AgentInfoForDID) |  | if there is an agent to which this identity belongs |






<a name="scuridplatformagentapi-v1-PostDeviceDataWithSignatureReq"></a>

### PostDeviceDataWithSignatureReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| dataSet | [PostDeviceDataWithSignatureStruct](#scuridplatformagentapi-v1-PostDeviceDataWithSignatureStruct) | repeated |  |






<a name="scuridplatformagentapi-v1-PostDeviceDataWithSignatureRes"></a>

### PostDeviceDataWithSignatureRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  |  |






<a name="scuridplatformagentapi-v1-PostDeviceDataWithSignatureStruct"></a>

### PostDeviceDataWithSignatureStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceDID | [string](#string) |  |  |
| deviceName | [string](#string) |  |  |
| dataTimestamp | [int32](#int32) |  |  |
| payload | [string](#string) |  |  |
| signature | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-RecordRejectedDIDReq"></a>

### RecordRejectedDIDReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |
| rejectedOn | [int64](#int64) |  | timestamp of rejection // UTC |
| isLocal | [bool](#bool) |  | defaults to false, if the identity was approved previously use that state |






<a name="scuridplatformagentapi-v1-RecordRejectedDIDRes"></a>

### RecordRejectedDIDRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  |  |






<a name="scuridplatformagentapi-v1-RegisterDeviceDIDReq"></a>

### RegisterDeviceDIDReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceDid | [string](#string) |  |  |
| platformDid | [string](#string) |  | platform did |
| isLocal | [bool](#bool) |  | if checked identites are not registered on DLT but only local database |






<a name="scuridplatformagentapi-v1-RegisterDeviceDIDRes"></a>

### RegisterDeviceDIDRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  |  |






<a name="scuridplatformagentapi-v1-RejectedIdentitiesListStruct"></a>

### RejectedIdentitiesListStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |
| vInfo | [string](#string) |  | edge agent version used for creating DID |
| rejectionTimestamp | [int64](#int64) |  |  |
| revokedOn | [int64](#int64) |  |  |
| created_on | [int64](#int64) |  |  |
| device_name | [string](#string) |  |  |
| isLocal | [bool](#bool) |  | if checked identities are not registered on DLT but only local database |
| deviceContext | [deviceContext.DeviceContext](#deviceContext-DeviceContext) |  | helps to onboard and bind a device to an identity |
| agentInfoForDID | [AgentInfoForDID](#scuridplatformagentapi-v1-AgentInfoForDID) |  | if there is an agent to which this identity belongs |






<a name="scuridplatformagentapi-v1-RemoveTagsReq"></a>

### RemoveTagsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tags | [TagStruct](#scuridplatformagentapi-v1-TagStruct) | repeated | tags to be deleted from the system |
| did | [string](#string) |  | this generally the device identity |






<a name="scuridplatformagentapi-v1-RemoveTagsRes"></a>

### RemoveTagsRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | boolean result, True if all gets deleted else false |






<a name="scuridplatformagentapi-v1-RequestIdentityStatusReq"></a>

### RequestIdentityStatusReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceDID | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-RequestIdentityStatusRes"></a>

### RequestIdentityStatusRes
response is one of the following


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-RequestRegistrationOfDeviceReq"></a>

### RequestRegistrationOfDeviceReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deviceDID | [string](#string) |  |  |
| requestedOn | [int64](#int64) |  | UTC timestamp of request from device, this value MUST come from device |
| vInfo | [string](#string) |  | edge agent version used for generating DID |
| device_name | [string](#string) |  | name with which customer, user identifies it uniquely, this could also be a name in the IIoT Platform |
| deviceContext | [deviceContext.DeviceContext](#deviceContext-DeviceContext) |  | helps to onboard and bind a device to an identity |
| signatureOnDeviceContext | [bytes](#bytes) |  | hash calculated on the fields requestedOn &#43; deviceDID. THIS must be sent by the agent and will be recorded on the backend and used for future verification. |
| agentInfoForDID | [AgentInfoForDID](#scuridplatformagentapi-v1-AgentInfoForDID) |  | if there is an agent to which this identity belongs |






<a name="scuridplatformagentapi-v1-RequestRegistrationOfDeviceRes"></a>

### RequestRegistrationOfDeviceRes
this only provides a confirmation if request has been successfully received.
Whether it&#39;s approved or rejected, will be handled by respective service
This info will be added to the Platform Agent&#39;s local storage


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  | only returns confirmation that the request has been received |






<a name="scuridplatformagentapi-v1-RevokeDeviceDIDReq"></a>

### RevokeDeviceDIDReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| device_did | [string](#string) |  |  |
| platform_did | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-RevokeDeviceDIDRes"></a>

### RevokeDeviceDIDRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  |  |






<a name="scuridplatformagentapi-v1-SignBytePayloadWithIdentityReq"></a>

### SignBytePayloadWithIdentityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| payload | [bytes](#bytes) |  | array if bytes to be signed |
| did | [string](#string) |  | identity i.e. did:scurid:XXXXXXXXXXX ; NOTE identity is case sensitive |






<a name="scuridplatformagentapi-v1-SignBytePayloadWithIdentityRes"></a>

### SignBytePayloadWithIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  | generated signature |






<a name="scuridplatformagentapi-v1-SignPayloadReq"></a>

### SignPayloadReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| payload | [string](#string) |  |  |
| did | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-SignPayloadRes"></a>

### SignPayloadRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-TagStruct"></a>

### TagStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tagName | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-UploadFilesReq"></a>

### UploadFilesReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| info | [FileInfo](#scuridplatformagentapi-v1-FileInfo) |  |  |
| chunkData | [bytes](#bytes) |  |  |






<a name="scuridplatformagentapi-v1-UploadFilesRes"></a>

### UploadFilesRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | true if successfully transferred the files. |






<a name="scuridplatformagentapi-v1-ValidIdentitiesListStruct"></a>

### ValidIdentitiesListStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| did | [string](#string) |  |  |
| vInfo | [string](#string) |  | edge agent version used for creating DID |
| created_on | [int64](#int64) |  |  |
| last_verified_on | [int64](#int64) |  |  |
| device_name | [string](#string) |  |  |
| isLocal | [bool](#bool) |  | if checked identities are not registered on DLT but only local database |
| path | [string](#string) |  | device pkg file store on the client side |
| deviceContext | [deviceContext.DeviceContext](#deviceContext-DeviceContext) |  | helps to onboard and bind a device to an identity |
| agentInfoForDID | [AgentInfoForDID](#scuridplatformagentapi-v1-AgentInfoForDID) |  | if there is an agent to which this identity belongs |






<a name="scuridplatformagentapi-v1-VerifyBytePayloadWithIdentityReq"></a>

### VerifyBytePayloadWithIdentityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  |  |
| payload | [bytes](#bytes) |  |  |
| did | [string](#string) |  | identity i.e. did:scurid:XXXXXXXXXXX ; NOTE: identity is case sensitive |






<a name="scuridplatformagentapi-v1-VerifyBytePayloadWithIdentityRes"></a>

### VerifyBytePayloadWithIdentityRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| isValid | [bool](#bool) |  | true if valid, else false (Defaults to False) |






<a name="scuridplatformagentapi-v1-VerifyDeviceDIDReq"></a>

### VerifyDeviceDIDReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| platform_did | [string](#string) |  |  |
| device_did | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-VerifyDeviceDIDRes"></a>

### VerifyDeviceDIDRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  |  |






<a name="scuridplatformagentapi-v1-VerifySignatureReq"></a>

### VerifySignatureReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  |  |
| payload | [string](#string) |  |  |
| did | [string](#string) |  |  |






<a name="scuridplatformagentapi-v1-VerifySignatureRes"></a>

### VerifySignatureRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| isValid | [bool](#bool) |  |  |





 

 

 


<a name="scuridplatformagentapi-v1-ScuridPlatformAgentAPI"></a>

### ScuridPlatformAgentAPI


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetPendingRequestsList | [GetPendingRequestsListReq](#scuridplatformagentapi-v1-GetPendingRequestsListReq) | [GetPendingRequestsListRes](#scuridplatformagentapi-v1-GetPendingRequestsListRes) | Track requests from new devices to register them on the SSI Service |
| VerifySignature | [VerifySignatureReq](#scuridplatformagentapi-v1-VerifySignatureReq) | [VerifySignatureRes](#scuridplatformagentapi-v1-VerifySignatureRes) | Verify signature of the payload Currently only string payloads are supported |
| CreateIdentity | [CreateIdentityReq](#scuridplatformagentapi-v1-CreateIdentityReq) | [CreateIdentityRes](#scuridplatformagentapi-v1-CreateIdentityRes) | Primarily to be used for DID Generation of the platform to be used for registering platform application for that customer This should make an internal call to the Scurid SSI Service and store the DID value in local storage in encrypted wallet |
| SignPayload | [SignPayloadReq](#scuridplatformagentapi-v1-SignPayloadReq) | [SignPayloadRes](#scuridplatformagentapi-v1-SignPayloadRes) | Sign a given payload with platform&#39;s DID |
| GetRejectedIdentitiesList | [GetRejectedIdentitiesListReq](#scuridplatformagentapi-v1-GetRejectedIdentitiesListReq) | [GetRejectedIdentitiesListRes](#scuridplatformagentapi-v1-GetRejectedIdentitiesListRes) | As platform agent must track every incoming request for DID registration in local DB storage, this service returns the list of all the DIDs that were rejected by the customer to be registered with Scurid SSI Service. This is mainly a bookkeeping service |
| GetValidIdentitiesList | [GetValidIdentitiesListReq](#scuridplatformagentapi-v1-GetValidIdentitiesListReq) | [GetValidIdentitiesListRes](#scuridplatformagentapi-v1-GetValidIdentitiesListRes) | Fetches the list of all the DIDs that were successfully registered in Scurid SSI Service, this list must be kept internally fresh by the platform&#39;s internal service |
| GetValidIdentityInfo | [GetValidIdentityInfoReq](#scuridplatformagentapi-v1-GetValidIdentityInfoReq) | [GetValidIdentityInfoRes](#scuridplatformagentapi-v1-GetValidIdentityInfoRes) | Fetches details available on a given identity in local DB storage, data on this identity must be kept fresh by internal services |
| RecordRejectedDID | [RecordRejectedDIDReq](#scuridplatformagentapi-v1-RecordRejectedDIDReq) | [RecordRejectedDIDRes](#scuridplatformagentapi-v1-RecordRejectedDIDRes) | Identities returned by GetPendingRequestsList if they are rejected by the customer from the flutter app, they of course MUST not be registered with Scurid SSI Service, but at the same time should be recorded in the local DB |
| RequestRegistrationOfDevice | [RequestRegistrationOfDeviceReq](#scuridplatformagentapi-v1-RequestRegistrationOfDeviceReq) | [RequestRegistrationOfDeviceRes](#scuridplatformagentapi-v1-RequestRegistrationOfDeviceRes) | this endpoint is for devices to call Platform Agent to register them Normally will be used by devices wanting to registering for the first time, or if a new DID has been generated on an existing device |
| RequestIdentityStatus | [RequestIdentityStatusReq](#scuridplatformagentapi-v1-RequestIdentityStatusReq) | [RequestIdentityStatusRes](#scuridplatformagentapi-v1-RequestIdentityStatusRes) | This endpoint is primarily meant for devices to get validation from Platform Application if their DID was registered on the blockchain |
| LocalStorageInit | [LocalStorageInitReq](#scuridplatformagentapi-v1-LocalStorageInitReq) | [LocalStorageInitRes](#scuridplatformagentapi-v1-LocalStorageInitRes) | To be called from desktop app for getting the path where DB should be initialized |
| GetAllDevicesList | [GetAllDevicesListReq](#scuridplatformagentapi-v1-GetAllDevicesListReq) | [GetAllDevicesListRes](#scuridplatformagentapi-v1-GetAllDevicesListRes) | A call to local storage to get list of all available device DIDs |
| VerifyDeviceDID | [VerifyDeviceDIDReq](#scuridplatformagentapi-v1-VerifyDeviceDIDReq) | [VerifyDeviceDIDRes](#scuridplatformagentapi-v1-VerifyDeviceDIDRes) | Wraps the call for SSI Service API with same name VerifyDeviceDID |
| RevokeDeviceDID | [RevokeDeviceDIDReq](#scuridplatformagentapi-v1-RevokeDeviceDIDReq) | [RevokeDeviceDIDRes](#scuridplatformagentapi-v1-RevokeDeviceDIDRes) | Wraps the call for SSI Service API with same name RevokeDeviceDID |
| RegisterDeviceDID | [RegisterDeviceDIDReq](#scuridplatformagentapi-v1-RegisterDeviceDIDReq) | [RegisterDeviceDIDRes](#scuridplatformagentapi-v1-RegisterDeviceDIDRes) | Wraps the call for SSI Service API with same name RegisterDeviceDID |
| GetPlatformDID | [GetPlatformDIDReq](#scuridplatformagentapi-v1-GetPlatformDIDReq) | [GetPlatformDIDRes](#scuridplatformagentapi-v1-GetPlatformDIDRes) | To provide Platform DID from the local gRPC platform storage |
| GetDevicePayloadsWithSignature | [GetDevicePayloadsWithSignatureReq](#scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureReq) | [GetDevicePayloadsWithSignatureRes](#scuridplatformagentapi-v1-GetDevicePayloadsWithSignatureRes) | Provides device&#39;s data with signature for each payload returned rows have boolean confirmation attached to each row True denotes that the device&#39;s payload has valid signature, false denotes otherwise |
| PostDeviceDataWithSignature | [PostDeviceDataWithSignatureReq](#scuridplatformagentapi-v1-PostDeviceDataWithSignatureReq) | [PostDeviceDataWithSignatureRes](#scuridplatformagentapi-v1-PostDeviceDataWithSignatureRes) | PostDeviceDataWithSignature to be called from edge devices to post / send their device data with signature to Platform |
| GetCountriesList | [GetCountriesListReq](#scuridplatformagentapi-v1-GetCountriesListReq) | [GetCountriesListRes](#scuridplatformagentapi-v1-GetCountriesListRes) | Provides list of countries |
| GetLicenseStatus | [GetLicenseStatusReq](#scuridplatformagentapi-v1-GetLicenseStatusReq) | [GetLicenseStatusRes](#scuridplatformagentapi-v1-GetLicenseStatusRes) |  |
| SignBytePayloadWithIdentity | [SignBytePayloadWithIdentityReq](#scuridplatformagentapi-v1-SignBytePayloadWithIdentityReq) | [SignBytePayloadWithIdentityRes](#scuridplatformagentapi-v1-SignBytePayloadWithIdentityRes) | Signs a byte array payload with identity |
| VerifyBytePayloadWithIdentity | [VerifyBytePayloadWithIdentityReq](#scuridplatformagentapi-v1-VerifyBytePayloadWithIdentityReq) | [VerifyBytePayloadWithIdentityRes](#scuridplatformagentapi-v1-VerifyBytePayloadWithIdentityRes) | Verifies a byte array payload with identity |
| AddTags | [AddTagsReq](#scuridplatformagentapi-v1-AddTagsReq) | [AddTagsRes](#scuridplatformagentapi-v1-AddTagsRes) | Adds tags for categorization of the identities |
| RemoveTags | [RemoveTagsReq](#scuridplatformagentapi-v1-RemoveTagsReq) | [RemoveTagsRes](#scuridplatformagentapi-v1-RemoveTagsRes) | Removes existing tags from the identity |
| GetTags | [GetTagsReq](#scuridplatformagentapi-v1-GetTagsReq) | [GetTagsRes](#scuridplatformagentapi-v1-GetTagsRes) stream | Get existing tags |
| AssignTagsToIdentity | [AssignTagsToIdentityReq](#scuridplatformagentapi-v1-AssignTagsToIdentityReq) | [AssignTagsToIdentityRes](#scuridplatformagentapi-v1-AssignTagsToIdentityRes) | AssignTagsToIdentity assign one more tags to an identity |
| ListIdentitiesUnderATag | [ListIdentitiesUnderATagReq](#scuridplatformagentapi-v1-ListIdentitiesUnderATagReq) | [ListIdentitiesUnderATagRes](#scuridplatformagentapi-v1-ListIdentitiesUnderATagRes) stream | Lists all the identities assigned to a Tag |
| UploadFiles | [UploadFilesReq](#scuridplatformagentapi-v1-UploadFilesReq) stream | [UploadFilesRes](#scuridplatformagentapi-v1-UploadFilesRes) | Used for uploading files to the server |
| DownloadFiles | [DownloadFilesReq](#scuridplatformagentapi-v1-DownloadFilesReq) | [DownloadFilesRes](#scuridplatformagentapi-v1-DownloadFilesRes) stream | Used for downloading device pkgs |
| FileStorePath | [FileStorePathReq](#scuridplatformagentapi-v1-FileStorePathReq) | [FileStorePathRes](#scuridplatformagentapi-v1-FileStorePathRes) | FileStorePath provides path for the device files |

 



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


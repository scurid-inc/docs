# Platform API v2 Documentation
<a name="top"></a>

## Table of Contents

- [platformapiv2.proto](#platformapiv2-proto)
    - [AgentsStruct](#platform-v2-AgentsStruct)
    - [ConfigureAgentReq](#platform-v2-ConfigureAgentReq)
    - [ConfigureAgentRes](#platform-v2-ConfigureAgentRes)
    - [CreateUserReq](#platform-v2-CreateUserReq)
    - [CreateUserRes](#platform-v2-CreateUserRes)
    - [DeleteUserReq](#platform-v2-DeleteUserReq)
    - [DeleteUserRes](#platform-v2-DeleteUserRes)
    - [DownloadReleaseZipReq](#platform-v2-DownloadReleaseZipReq)
    - [DownloadReleaseZipRes](#platform-v2-DownloadReleaseZipRes)
    - [DownloadReq](#platform-v2-DownloadReq)
    - [DownloadRes](#platform-v2-DownloadRes)
    - [GetAgentInfoReq](#platform-v2-GetAgentInfoReq)
    - [GetAgentInfoRes](#platform-v2-GetAgentInfoRes)
    - [GetAgentsListReq](#platform-v2-GetAgentsListReq)
    - [GetAgentsListRes](#platform-v2-GetAgentsListRes)
    - [GetAppLogsReq](#platform-v2-GetAppLogsReq)
    - [GetAppLogsRes](#platform-v2-GetAppLogsRes)
    - [GetAppOnboardingInfoReq](#platform-v2-GetAppOnboardingInfoReq)
    - [GetAppOnboardingInfoRes](#platform-v2-GetAppOnboardingInfoRes)
    - [GetIDSettingsReq](#platform-v2-GetIDSettingsReq)
    - [GetIDSettingsRes](#platform-v2-GetIDSettingsRes)
    - [GetIdentityInfoReq](#platform-v2-GetIdentityInfoReq)
    - [GetIdentityInfoRes](#platform-v2-GetIdentityInfoRes)
    - [GetIdentityLogReq](#platform-v2-GetIdentityLogReq)
    - [GetIdentityLogRes](#platform-v2-GetIdentityLogRes)
    - [GetIntegrationConfigReq](#platform-v2-GetIntegrationConfigReq)
    - [GetIntegrationConfigRes](#platform-v2-GetIntegrationConfigRes)
    - [GetReleasesReq](#platform-v2-GetReleasesReq)
    - [GetReleasesRes](#platform-v2-GetReleasesRes)
    - [GetUserInfoReq](#platform-v2-GetUserInfoReq)
    - [GetUserInfoRes](#platform-v2-GetUserInfoRes)
    - [GetUsersReq](#platform-v2-GetUsersReq)
    - [GetUsersRes](#platform-v2-GetUsersRes)
    - [InviteUserReq](#platform-v2-InviteUserReq)
    - [InviteUserRes](#platform-v2-InviteUserRes)
    - [RecordAppLogsReq](#platform-v2-RecordAppLogsReq)
    - [RecordAppLogsRes](#platform-v2-RecordAppLogsRes)
    - [RegisterAgentReq](#platform-v2-RegisterAgentReq)
    - [RegisterAgentRes](#platform-v2-RegisterAgentRes)
    - [RequestRegistrationCodeReq](#platform-v2-RequestRegistrationCodeReq)
    - [RequestRegistrationCodeRes](#platform-v2-RequestRegistrationCodeRes)
    - [ResetPasswordReq](#platform-v2-ResetPasswordReq)
    - [ResetPasswordRes](#platform-v2-ResetPasswordRes)
    - [RevokeAgentReq](#platform-v2-RevokeAgentReq)
    - [RevokeAgentRes](#platform-v2-RevokeAgentRes)
    - [ScuridAppOnboardingInfo](#platform-v2-ScuridAppOnboardingInfo)
    - [SetIDSettingsReq](#platform-v2-SetIDSettingsReq)
    - [SetIDSettingsRes](#platform-v2-SetIDSettingsRes)
    - [StoreAppOnboardingInfoReq](#platform-v2-StoreAppOnboardingInfoReq)
    - [StoreAppOnboardingInfoRes](#platform-v2-StoreAppOnboardingInfoRes)
    - [StoreIntegrationConfigReq](#platform-v2-StoreIntegrationConfigReq)
    - [StoreIntegrationConfigRes](#platform-v2-StoreIntegrationConfigRes)
    - [UpdateUserPasswordReq](#platform-v2-UpdateUserPasswordReq)
    - [UpdateUserPasswordRes](#platform-v2-UpdateUserPasswordRes)
    - [VerifyAgentReq](#platform-v2-VerifyAgentReq)
    - [VerifyAgentRes](#platform-v2-VerifyAgentRes)
  
    - [Platform](#platform-v2-Platform)
    - [Subsystems](#platform-v2-Subsystems)
  
- [Scalar Value Types](#scalar-value-types)



<a name="platformapiv2-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## platformapiv2.proto



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
| integrationDetails | [integration.IntegrationDetails](#integration-IntegrationDetails) |  | default is nil, if agent is configured with any integration, this will be populated |
| signatureOnIntegration | [signature.Signature](#signature-Signature) |  | signature of the Scurid Server&#39;s identity on the integration details. This is used to verify the integrity of the integration details. |
| storageSchemaMetadata | [storageSchemaMetadata.StoreSchemaMetadataRequest](#storageSchemaMetadata-StoreSchemaMetadataRequest) |  | default is nil, if agent is configured with any storage schema, this will be populated |
| storageTableName | [string](#string) |  |  |






<a name="platform-v2-ConfigureAgentReq"></a>

### ConfigureAgentReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentID | [string](#string) |  | AgentID is the DID of the agent to be configured |
| integrationDetails | [integration.IntegrationDetails](#integration-IntegrationDetails) |  | IntegrationDetails is the configuration to be applied to the agent |
| agentAlias | [string](#string) |  | agentAlias custom alias for the agent |
| storeSchemaMetadataRequest | [storageSchemaMetadata.StoreSchemaMetadataRequest](#storageSchemaMetadata-StoreSchemaMetadataRequest) |  | defines the storage schema structure applied to the agent data storage |
| storageTableName | [string](#string) |  | defines the storage table name for the agent data storage this will be used for creating the database table name; in reference to the RDBMS storage structure |






<a name="platform-v2-ConfigureAgentRes"></a>

### ConfigureAgentRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [bool](#bool) |  | Status is the status of the configuration operation |






<a name="platform-v2-CreateUserReq"></a>

### CreateUserReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user | [user.v1.User](#user-v1-User) |  |  |
| userData | [user.v1.UserData](#user-v1-UserData) |  |  |
| inviteKey | [string](#string) |  | this is the key that will be used to invite the user, and would have been sent to the user when sending the invite. |






<a name="platform-v2-CreateUserRes"></a>

### CreateUserRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  |  |






<a name="platform-v2-DeleteUserReq"></a>

### DeleteUserReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |






<a name="platform-v2-DeleteUserRes"></a>

### DeleteUserRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  |  |






<a name="platform-v2-DownloadReleaseZipReq"></a>

### DownloadReleaseZipReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| version | [string](#string) |  |  |






<a name="platform-v2-DownloadReleaseZipRes"></a>

### DownloadReleaseZipRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| file | [release.CompleteReleaseZip](#release-CompleteReleaseZip) |  |  |






<a name="platform-v2-DownloadReq"></a>

### DownloadReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| asset | [release.Asset](#release-Asset) | repeated |  |






<a name="platform-v2-DownloadRes"></a>

### DownloadRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| version | [release.DownloadVersion](#release-DownloadVersion) |  |  |






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






<a name="platform-v2-GetAppOnboardingInfoReq"></a>

### GetAppOnboardingInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| platformIdentity | [string](#string) |  |  |






<a name="platform-v2-GetAppOnboardingInfoRes"></a>

### GetAppOnboardingInfoRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| onboardingInfo | [ScuridAppOnboardingInfo](#platform-v2-ScuridAppOnboardingInfo) |  |  |






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






<a name="platform-v2-GetIntegrationConfigReq"></a>

### GetIntegrationConfigReq
left empty






<a name="platform-v2-GetIntegrationConfigRes"></a>

### GetIntegrationConfigRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| thingworx | [integration.ThingWorx](#integration-ThingWorx) |  |  |
| hawkbit | [integration.Hawkbit](#integration-Hawkbit) |  |  |
| azure | [integration.Azure](#integration-Azure) |  |  |






<a name="platform-v2-GetReleasesReq"></a>

### GetReleasesReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| timestamp | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  | use this to filter the releases; field is optional |
| version | [google.protobuf.StringValue](#google-protobuf-StringValue) |  | use this to filter the releases; if not provided, field is optional |






<a name="platform-v2-GetReleasesRes"></a>

### GetReleasesRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| list | [release.ReleaseStruct](#release-ReleaseStruct) | repeated |  |






<a name="platform-v2-GetUserInfoReq"></a>

### GetUserInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |






<a name="platform-v2-GetUserInfoRes"></a>

### GetUserInfoRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| userData | [user.v1.UserData](#user-v1-UserData) |  |  |
| userOperation | [user.v1.UserOperation](#user-v1-UserOperation) |  |  |
| role | [user.v1.Role](#user-v1-Role) |  |  |
| inviteKey | [string](#string) |  | this is the key that will be used to invite the user, and would have been sent to the user when sending the invite. |






<a name="platform-v2-GetUsersReq"></a>

### GetUsersReq
left empty






<a name="platform-v2-GetUsersRes"></a>

### GetUsersRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| usersList | [string](#string) | repeated |  |






<a name="platform-v2-InviteUserReq"></a>

### InviteUserReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| userInvite | [user.v1.UserInvite](#user-v1-UserInvite) |  |  |






<a name="platform-v2-InviteUserRes"></a>

### InviteUserRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  |  |






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






<a name="platform-v2-RequestRegistrationCodeReq"></a>

### RequestRegistrationCodeReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |






<a name="platform-v2-RequestRegistrationCodeRes"></a>

### RequestRegistrationCodeRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | if a valid email was received server will send a code and return here true; else false |






<a name="platform-v2-ResetPasswordReq"></a>

### ResetPasswordReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |






<a name="platform-v2-ResetPasswordRes"></a>

### ResetPasswordRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | if a valid email was received server will send a code and return here true; else false |






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






<a name="platform-v2-ScuridAppOnboardingInfo"></a>

### ScuridAppOnboardingInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| onboardingInfo | [string](#string) |  | this must be a json formatted string |






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






<a name="platform-v2-StoreAppOnboardingInfoReq"></a>

### StoreAppOnboardingInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| platformIdentity | [string](#string) |  |  |
| onboardingInfo | [ScuridAppOnboardingInfo](#platform-v2-ScuridAppOnboardingInfo) |  |  |






<a name="platform-v2-StoreAppOnboardingInfoRes"></a>

### StoreAppOnboardingInfoRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  |  |






<a name="platform-v2-StoreIntegrationConfigReq"></a>

### StoreIntegrationConfigReq
StoreIntegrationConfigReq send one or all config at once


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| thingworx | [integration.ThingWorx](#integration-ThingWorx) |  |  |
| hawkbit | [integration.Hawkbit](#integration-Hawkbit) |  |  |
| azure | [integration.Azure](#integration-Azure) |  |  |






<a name="platform-v2-StoreIntegrationConfigRes"></a>

### StoreIntegrationConfigRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | default is false, if successful returns True |






<a name="platform-v2-UpdateUserPasswordReq"></a>

### UpdateUserPasswordReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |
| code | [string](#string) |  |  |
| newPassword | [bytes](#bytes) |  |  |






<a name="platform-v2-UpdateUserPasswordRes"></a>

### UpdateUserPasswordRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | if user was updated successfully return true; else false |






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
| ConfigureAgent | [ConfigureAgentReq](#platform-v2-ConfigureAgentReq) | [ConfigureAgentRes](#platform-v2-ConfigureAgentRes) | ConfigureAgent helps modify Scurid Edge Agent behaviour |


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
| StoreIntegrationConfig | [StoreIntegrationConfigReq](#platform-v2-StoreIntegrationConfigReq) | [StoreIntegrationConfigRes](#platform-v2-StoreIntegrationConfigRes) | Stores Integration configuration in Scurid Server storage This is a global configuration and will be used by all identities |
| GetIntegrationConfig | [GetIntegrationConfigReq](#platform-v2-GetIntegrationConfigReq) | [GetIntegrationConfigRes](#platform-v2-GetIntegrationConfigRes) | GetIntegrationConfig fetches currently stored integration configuration from Scurid Server This is a global configuration and will be used by all identities |
| StoreAppOnboardingInfo | [StoreAppOnboardingInfoReq](#platform-v2-StoreAppOnboardingInfoReq) | [StoreAppOnboardingInfoRes](#platform-v2-StoreAppOnboardingInfoRes) | Stores the user onboarding information created |
| GetAppOnboardingInfo | [GetAppOnboardingInfoReq](#platform-v2-GetAppOnboardingInfoReq) | [GetAppOnboardingInfoRes](#platform-v2-GetAppOnboardingInfoRes) | Fetches the user onboarding information created |
| CreateUser | [CreateUserReq](#platform-v2-CreateUserReq) | [CreateUserRes](#platform-v2-CreateUserRes) | Creates a new App User in the Scurid Server |
| InviteUser | [InviteUserReq](#platform-v2-InviteUserReq) | [InviteUserRes](#platform-v2-InviteUserRes) | Sends invite to a new user |
| GetUsers | [GetUsersReq](#platform-v2-GetUsersReq) | [GetUsersRes](#platform-v2-GetUsersRes) | GetUsers returns list of users |
| DeleteUser | [DeleteUserReq](#platform-v2-DeleteUserReq) | [DeleteUserRes](#platform-v2-DeleteUserRes) | DeleteUser deletes a user |
| GetUserInfo | [GetUserInfoReq](#platform-v2-GetUserInfoReq) | [GetUserInfoRes](#platform-v2-GetUserInfoRes) | GetUserInfo returns user info |
| ResetPassword | [ResetPasswordReq](#platform-v2-ResetPasswordReq) | [ResetPasswordRes](#platform-v2-ResetPasswordRes) | Resets the password of a user |
| UpdateUserPassword | [UpdateUserPasswordReq](#platform-v2-UpdateUserPasswordReq) | [UpdateUserPasswordRes](#platform-v2-UpdateUserPasswordRes) | UpdateUserPassword updates the user |
| GetReleases | [GetReleasesReq](#platform-v2-GetReleasesReq) | [GetReleasesRes](#platform-v2-GetReleasesRes) | Get versions list |
| Download | [DownloadReq](#platform-v2-DownloadReq) | [DownloadRes](#platform-v2-DownloadRes) stream | Called by clients to Download file(s) |
| DownloadReleaseZip | [DownloadReleaseZipReq](#platform-v2-DownloadReleaseZipReq) | [DownloadReleaseZipRes](#platform-v2-DownloadReleaseZipRes) stream | Request to download a zip file, containing all the files in the release from Edge Agent, Server &amp; App etc. Request only need the version number |
| RequestRegistrationCode | [RequestRegistrationCodeReq](#platform-v2-RequestRegistrationCodeReq) | [RequestRegistrationCodeRes](#platform-v2-RequestRegistrationCodeRes) | RequestRegistrationCode generates a registration code for the user Call this API if the code which user has, has already expire or is invalid |

 



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


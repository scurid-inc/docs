# Integration API Documentation
<a name="top"></a>

## Table of Contents

- [integration.proto](#integration-proto)
    - [Azure](#integration-Azure)
    - [Hawkbit](#integration-Hawkbit)
    - [IntegrationDetails](#integration-IntegrationDetails)
    - [IntegrationStatus](#integration-IntegrationStatus)
    - [ThingWorx](#integration-ThingWorx)
  
- [Scalar Value Types](#scalar-value-types)



<a name="integration-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## integration.proto



<a name="integration-Azure"></a>

### Azure
For Azure IoT &amp; Azure Device Provisioning Service


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| csrSigningCertificate | [bytes](#bytes) |  | this is the certificate used to sign the CSR to issue device certificates |
| privateKey | [bytes](#bytes) |  | this is the private key used to sign the CSR to issue device certificates |






<a name="integration-Hawkbit"></a>

### Hawkbit
For Hawkbit Server


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| hawkbitURL | [string](#string) |  | hawkbit server URL &amp; port information e.g. https://localhost:8080 |
| username | [string](#string) |  | username from Hawkbit server |
| password | [string](#string) |  | password from Hawkbit server |






<a name="integration-IntegrationDetails"></a>

### IntegrationDetails
IntegrationDetails contains information on integration with 3rd party platforms


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| hawkbitTargetSecretKey | [string](#string) |  | a target in Hawkbit is device, when a device is pre-provisioned it will create a secret key which is specific to each device |
| deviceCertificateSigningRequest | [string](#string) |  | this is the certificate signing request received from the agent. |
| deviceCertificate | [bytes](#bytes) |  | if Azure is enabled, and agent is approved, scurid server will sign the request to generate the certificate, which we can store here |
| integrationStatus | [IntegrationStatus](#integration-IntegrationStatus) |  |  |
| thingworxApplicationKey | [string](#string) |  | this is the device application key issued from ThingWorx |
| thingworxAppKeyName | [string](#string) |  | this is the name of the app key in ThingWorx |
| csrCustom | [certificate.v1.CSRCustom](#certificate-v1-CSRCustom) |  | this is the custom CSR information |






<a name="integration-IntegrationStatus"></a>

### IntegrationStatus
IntegrationStatus should be used to track which 3rd party integrations are enabled.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| thingWorxEnabled | [bool](#bool) |  | is thingworx integration enabled |
| hawkbitEnabled | [bool](#bool) |  | is hawkbit integration enabled |
| azureEnabled | [bool](#bool) |  | is azure integration enabled |






<a name="integration-ThingWorx"></a>

### ThingWorx
For Thingworx Server


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| thingWorxURL | [string](#string) |  | thingworx server and port information e.g. https://localhost:443/Thingworx |
| appKey | [string](#string) |  | thingworx app key created for Scurid server to authenticate with |
| useThingWorxEntityNameToDownloadAppKey | [bool](#bool) |  | if true, then the app key will be downloaded from thingworx using the entity name |





 

 

 

 



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


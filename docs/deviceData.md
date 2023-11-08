# Device Data API Documentation
<a name="top"></a>

## Table of Contents

- [deviceData.proto](#deviceData-proto)
    - [BeaconStructure](#deviceData-BeaconStructure)
    - [DataPacketMetadata](#deviceData-DataPacketMetadata)
    - [DataTimestamp](#deviceData-DataTimestamp)
    - [DeviceData](#deviceData-DeviceData)
    - [GetAgentDataReq](#deviceData-GetAgentDataReq)
    - [GetAgentDataRes](#deviceData-GetAgentDataRes)
    - [GetAgentDataStatReq](#deviceData-GetAgentDataStatReq)
    - [GetAgentDataStatRes](#deviceData-GetAgentDataStatRes)
    - [MaWaRouteDataStruct](#deviceData-MaWaRouteDataStruct)
    - [QueryStruct](#deviceData-QueryStruct)
  
- [Scalar Value Types](#scalar-value-types)



<a name="deviceData-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## deviceData.proto



<a name="deviceData-BeaconStructure"></a>

### BeaconStructure



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uuid | [string](#string) |  |  |
| major | [int32](#int32) |  |  |
| minor | [int32](#int32) |  |  |
| rssi | [int32](#int32) |  |  |






<a name="deviceData-DataPacketMetadata"></a>

### DataPacketMetadata



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| signature | [string](#string) |  |  |






<a name="deviceData-DataTimestamp"></a>

### DataTimestamp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| timestamp | [int64](#int64) |  | device&#39;s UTC timestamp UNIX nanoseconds |






<a name="deviceData-DeviceData"></a>

### DeviceData



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| timestamp | [DataTimestamp](#deviceData-DataTimestamp) |  |  |
| data | [string](#string) |  | contains device data formatted in json |
| metadata | [DataPacketMetadata](#deviceData-DataPacketMetadata) |  |  |






<a name="deviceData-GetAgentDataReq"></a>

### GetAgentDataReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentID | [string](#string) |  |  |
| query | [QueryStruct](#deviceData-QueryStruct) |  |  |






<a name="deviceData-GetAgentDataRes"></a>

### GetAgentDataRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [DeviceData](#deviceData-DeviceData) |  | json data stored in the database |
| deviceDataColumnNames | [string](#string) |  | json formatted column names |






<a name="deviceData-GetAgentDataStatReq"></a>

### GetAgentDataStatReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| agentID | [string](#string) |  |  |






<a name="deviceData-GetAgentDataStatRes"></a>

### GetAgentDataStatRes



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| dataCount | [int64](#int64) |  |  |
| totalVerifiableData | [int64](#int64) |  |  |
| totalUnverifiableData | [int64](#int64) |  |  |
| listOfUnverifiableData | [int64](#int64) | repeated | todo: send list of rowid in the future |
| statsLastUpdatedOn | [int64](#int64) |  |  |




<a name="deviceData-QueryStruct"></a>

### QueryStruct
used for querying data from the backend for a specific time range


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| startTimestamp | [int64](#int64) |  |  |
| endTimestamp | [int64](#int64) |  |  |





 

 

 

 



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


# Device Data Documentation
<a name="top"></a>

## Table of Contents

- [deviceData.proto](#deviceData-proto)
    - [BeaconStructure](#deviceData-BeaconStructure)
    - [DataPacketMetadata](#deviceData-DataPacketMetadata)
    - [DataTimestamp](#deviceData-DataTimestamp)
    - [DeviceData](#deviceData-DeviceData)
    - [GpsCoords](#deviceData-GpsCoords)
    - [MaWaRouteDataStruct](#deviceData-MaWaRouteDataStruct)
  
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
| data | [string](#string) |  | contains device data |
| metadata | [DataPacketMetadata](#deviceData-DataPacketMetadata) |  |  |






<a name="deviceData-GpsCoords"></a>

### GpsCoords



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| latitude | [string](#string) |  |  |
| longitude | [string](#string) |  |  |






<a name="deviceData-MaWaRouteDataStruct"></a>

### MaWaRouteDataStruct



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| timestamp | [DataTimestamp](#deviceData-DataTimestamp) |  |  |
| beacon | [BeaconStructure](#deviceData-BeaconStructure) | optional |  |
| gpsCoords | [GpsCoords](#deviceData-GpsCoords) | optional |  |
| metadata | [DataPacketMetadata](#deviceData-DataPacketMetadata) |  |  |





 

 

 

 



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


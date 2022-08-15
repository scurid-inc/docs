# Device Context

#### Reference file : deviceContext.proto

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


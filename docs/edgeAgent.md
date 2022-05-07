These are the set of APIs that are exposed when running `Scurid Edge Agent` on an IoT device.

## ScuridEdgeAgentAPI Endpoint group


| Endpoint Name                 | Description                                                                                                                                                                                                                                          |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CreateDeviceIdentity          | Called directly on the device to generate a new device identity.                                                                                                                                                                                     |
| DeleteDeviceDID               | Deletes any existing device identity from the Iot device.                                                                                                                                                                                            |
| GetDeviceIdentity             | Validates if particular identity was already created locally.                                                                                                                                                                                        |
| GetScuridEdgeAgentVersion     | Get currently installed version of edge agent.                                                                                                                                                                                                       |
| SignWithIdentity              | Signs a payload with identity.                                                                                                                                                                                                                       |
| VerifySignature               | Verifies a signature tagged to the payload.                                                                                                                                                                                                          |
| SignBytePayloadWithIdentity   | Signs a byte array payload with identity.                                                                                                                                                                                                            |
| VerifyBytePayloadWithIdentity | Verifies a byte array payload with identity.                                                                                                                                                                                                         |
| RegisterDeviceIdentity        | To be called for registering the device identity for the first time. Expects additional device data that will be used for binding the identity with the device.                                                                                      |
| GetToken                      | GetToken to receive required token from Scurid Platform App. Needed in order to access APIs that need authentication from the Scurid Platform App. Not used for authentication locally on the Scurid Edge Agent. Also used for refreshing the token. |
| DownloadFiles                 | Used for downloading one or more files. number of files to download will depend on files prepared by the admin on Scurid Platform App.                                                                                                               |


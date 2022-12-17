This tutorial provides a simplified overview on generating, approving device identity with the microscurid-c library, and approving it using Scurid Platform App.

## Initial setup

We will use the example code in the microscurid-c library.

### 1. Server and MCU setup

First, we need to have the server and the MCU ready.

- You will need to run the Scurid server binary on a machine of your choice (we will skip the details in this blog). Make sure to have the specific port (in this tutorial, `8888`) open so that the MCU can make requests to the server.
- The microscurid-c library currently works on the STM32WB55 series. Another adapter to connect to the ethernet may be needed as well.

### 2. Preparation on the MCU side: configuring the network info

We will use the example code in the microscurid-c library.

#### 1. Configure the network

Before compiling and transferring the example code to our MCU, we first need to configure the network settings. In `app_freertos.c`, configure the server port and IP address as below.

```
#define BACKEND_SERVER_PORT 8888
...
unsigned char BACKEND_SERVER_IP[4] = {192,168,151,128};
```

We will also need to configure the subnet mask and gateway server IP address, and whether we want to enable DHCP.

```
static wiz_NetInfo g_net_info = { .mac = { 0x00, 0x00, 0x00, 0x00, 0x00, 0x00 },// MAC address, we fill them with zeros since they are unnecessary for now
		.ip = { 192, 168, 151, 127 },                    // // IP address, fill in random numbers if using DHCP
		.sn = { 255, 255, 254, 0 },                    	// Subnet Mask
		.gw = { 192, 168, 150, 1 },                     // Gateway
		.dns = { 192, 168, 150, 1 },                    // DNS server
		.dhcp = NETINFO_DHCP                       	// DHCP enable/disable
		};
```

#### 2. Paste your certificate

We also need to paste the certificate to use for encryption in `Drivers/TLS/certificate.h`.

```Drivers/TLS/certificate.h

const char	self_signed_certificate[] =	\
"-----BEGIN CERTIFICATE-----\n" \
"MIIGTjCCBDagAwIBAgIUAKvvmZw3VLawhM9mvTKFJubPj78wDQYJKoZIhvcNAQEL\n" \
"BQAwZDELMAkGA1UEBhMCanAxDjAMBgNVBAgTBXRva3lvMQ4wDAYDVQQHEwV0b2t5\n" \
"...\n" \
"bzEPMA0GA1UEChMGc2N1cmlkMQ8wDQYDVQQLEwZzY3VyaWQxEzARBgNVBAMTCnNj\n" \
"dXJpZC5jb20wHhcNMjIwOTI4MDQyODQ2WhcNMzExMjI4MjA0NTUxWjBkMQswCQYD\n" \
"D+mhQS2JfxyOjx2RmiJUqTCJRBvSTk0DfMItaFxV+BJ5nA==\n" \
"-----END CERTIFICATE-----\n";

```

#### 3. Fix the conflict between macros.

There may also be some conflicts between the W5500 and STM32 library.
Modify `MR` => `W_MR` in the following file.

```/p-nucleo-wb55/Middlewares/ioLibrary_Driver/Ethernet/W5500/w5500.h
/**
 * @ingroup Common_register_group
 * @brief Mode Register address(R/W)\n
 * @ref MR is used for S/W reset, ping block mode, PPPoE mode and etc.
 * @details Each bit of @ref MR defined as follows.
 * <table>
 * 		<tr>  <td>7</td> <td>6</td> <td>5</td> <td>4</td> <td>3</td> <td>2</td> <td>1</td> <td>0</td>   </tr>
 * 		<tr>  <td>RST</td> <td>Reserved</td> <td>WOL</td> <td>PB</td> <td>PPPoE</td> <td>Reserved</td> <td>FARP</td> <td>Reserved</td> </tr>
 * </table>
 * - \ref MR_RST		 	: Reset
 * - \ref MR_WOL       	: Wake on LAN
 * - \ref MR_PB         : Ping block
 * - \ref MR_PPPOE      : PPPoE mode
 * - \ref MR_FARP			: Force ARP mode
 */
#define W_MR                 (_W5500_IO_BASE_ + (0x0000 << 8) + (WIZCHIP_CREG_BLOCK << 3))

// ...............

/////////////////////////////////
// Common Register I/O function //
/////////////////////////////////
/**
 * @ingroup Common_register_access_function
 * @brief Set Mode Register
 * @param (uint8_t)mr The value to be set.
 * @sa getMR()
 */
#define setMR(mr) \
	WIZCHIP_WRITE(W_MR,mr)


/**
 * @ingroup Common_register_access_function
 * @brief Get Mode Register
 * @return uint8_t. The value of Mode register.
 * @sa setMR()
 */
#define getMR() \
		WIZCHIP_READ(W_MR)
```

In this tutorial, we are using the STM32 Cube IDE.

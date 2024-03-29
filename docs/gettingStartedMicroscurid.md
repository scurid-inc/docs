## Getting Started with MicroScurid

### Overview

MicroScurid-c is the C implementation of some features from Scurid Edge Agent.
MicroScurid-c can be used to generate identities and register them on the server via TLS communication on Microcontrollers(MCUs) and Linux systems.
For communication with Scurid Server it utilizes data structures defined and governed by standard proto buffers, via Nanopb library.

### Getting access to the library

Contact us at info@scurid.com

### Platform Details

=== "STM32"

    Microscurid-c works on the [STM32WB Series](https://www.st.com/en/microcontrollers-microprocessors/stm32wb-series.html).
    A separate adapter for ethernet connection may be needed, e.g. [PoE FeatherWing](https://www.crowdsupply.com/silicognition/poe-featherwing)

    Getting started with the example code may help you grasp the idea of what Microscurid-c is doing.
    Below are the instructions of how to configure the network and timestamp settings.

    #### Configuring the server IP / gateway IP / server port

    The gateway IP, subnet masks, etc. can be configured in
    `examples/p-nucleo-wb55/Core/Src/app_freertos.c`.

    ```
    #define BACKEND_SERVER_PORT 8888

    static wiz_NetInfo g_net_info = { .mac = { 0x00, 0x00, 0x00, 0x00, 0x00, 0x00 },// MAC address
            .ip = { 192, 168, 151, 127 },                    // IP address
            .sn = { 255, 255, 254, 0 },                    	// Subnet Mask
            .gw = { 192, 168, 150, 1 },                     // Gateway
            .dns = { 192, 168, 150, 1 },                    // DNS server
            .dhcp = NETINFO_DHCP                       	// DHCP enable/disable
            };

    unsigned char BACKEND_SERVER_IP[4] = {192,168,151,128};
    ```

    #### Configuring the RTC timer

    The RTC timer must be configured to provide an accurate timestamp.
    Configure them here in: `microscurid-c/examples/p-nucleo-wb55/Core/Src/main.c`

    ```
    sTime.Hours = 0x11;
    sTime.Minutes = 0x32;
    sTime.Seconds = 0x0;
    sTime.SubSeconds = 0x0;
    sTime.DayLightSaving = RTC_DAYLIGHTSAVING_NONE;
    sTime.StoreOperation = RTC_STOREOPERATION_RESET;
    if (HAL_RTC_SetTime(&hrtc, &sTime, RTC_FORMAT_BCD) != HAL_OK)
    {
        Error_Handler();
    }
    sDate.WeekDay = RTC_WEEKDAY_SATURDAY;
    sDate.Month = RTC_MONTH_NOVEMBER;
    sDate.Date = 0x26;
    sDate.Year = 0x2022;
    ```

=== "Linux"

    Coming soon.

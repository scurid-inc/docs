## Overview

Microscurid enables you to create identities on your MCUs.

## Pre-requisites

You must download the microscurid-c library.

## Steps

You must include the header file and create the DID

=== "STM32"
    ```c
    #include "microscurid.h"

    {
        scurid_did_t did;
        while (create_identity(task_interface->hrng, &did) == -1)
        {
            printf("Error generating did, trying again in 100ms...\r\n");
            HAL_Delay(100);
        }

        printf("\ndid:%s:%s\r\n\n", did.method, did.identifier);
    }
    ```


=== "AMD64"
    ```c
    #include "microscurid.h"

    int main(void) {
        scurid_did_t did;

        create_identity(&did);
        return 0;
    }
    ```
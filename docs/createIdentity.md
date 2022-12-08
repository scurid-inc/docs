## Overview

Microscurid enables you to create identities on your MCUs.

## Pre-requisites

You must download the microscurid-c library.

## Steps

=== "STM32"

Pass the random number generator and the pointer of the DID struct to the `create_identity` function.

    ```c
    #include "microscurid.h"

...

    scurid_did_t did;
    while (create_identity(task_interface->hrng, &did) == -1)
    {
        printf("Error generating did, trying again in 100ms...\r\n");
        HAL_Delay(100);
    }
    ```


=== "AMD64"

Pass the pointer of the DID struct to the `create_identity` function.

    ```c
    #include "microscurid.h"

    int main(void) {
        scurid_did_t did;

        create_identity(&did);
    }

    return 0;
    ```
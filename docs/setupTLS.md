#### Adding the certificate

=== "STM32"

    Add the content of the certificate to `examples/p-nucleo-wb55/Drivers/TLS/certificate.h`.

=== "AMD64"

    Place the certificate file to the same directory as the binary file to be run.

#### Actual code


=== "STM32"
    ```c
    wiz_tls_context tlsContext;

	ret = wiz_tls_init(&tlsContext,&server_fd); // should return 1

	ret = wiz_tls_connect(&tlsContext, BACKEND_PORT, gServer_IP); // should return 0

    while (create_identity(task_interface->hrng, &did) == -1)
    {
        printf("Error generating did, trying again in 100ms...\r\n");
        HAL_Delay(100);
    }

    printf("\ndid:%s:%s\r\n\n", did.method, did.identifier);


    //make_json_didinfo(g_send_buf, &data_len, &did);

    data_len = create_data_buffer(&did, g_send_buf, timestamp);
    // printf("buffer size, %d", data_len);

    printf("%s : %d \r\n",g_send_buf, len);
    /*  Write data to the SSL channel  */
    ret = wiz_tls_write(&tlsContext, g_send_buf, data_len);
    ```

=== "AMD64"
    ```c
    scurid_did_t did;

    create_identity(&did);

    run_tcp_client(did);
    ```
    Pass the DID to the `run_tcp_client` function.
    The TCP client with TLS will send the data to the Scurid server.
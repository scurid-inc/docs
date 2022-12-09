## Getting Started with Microscurid

### Overview

Microscurid-c is the C implementation of some of the features from Scurid Edge Agents.
Microscurid-c can be used to generate identities and register them on the server via TLS communication on MCUs and Linux systems.

### Setting up

The library can be compiled for both AMD64 and STM32 architectures using `make`

```
$ make
```

It is possible to compile only for one architecture:

=== "amd64"
    ```shell
    $ make amd64
    ```

=== "stm32wb55"
    ```shell
    $ make stm32wb55
    ```

### Platform Details

#### Microcontroller

#### Linux
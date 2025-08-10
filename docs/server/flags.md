# Command-line flags

Flags to help you configure the server at startup. These flags can be set in the command line when starting the server.

| Flag           | Default              | Description                                                                                                  |
|----------------|----------------------|--------------------------------------------------------------------------------------------------------------|
| -port          | 8082                 | Sets the main server port (legacy/unused in current startup; kept for compatibility).                        |
| -keystore      | keys/                | Filesystem path where the platform key store is located.                                                     |
| -scuridservice | beta2.scurid.com:443 | DO NOT EDIT until Scurid officially publishes new address of the Scurid SSI service the backend connects to. |
| -pkgstore      | devicepkg/           | Directory for device packages and related artifacts.                                                         |
| -authport      | 8083                 | Port for the (optional) Auth HTTP server.                                                                    |
| -tcp           | :8888                | TCP API server bind address for plain HTTP/TCP endpoints.                                                    |
| -serverconfig  | config/config.yaml   | Path to the primary server YAML configuration file.                                                          |
| -monitor       | true                 | Enables Prometheus metrics and starts the metrics HTTP server when true.                                     |
| -log           | log/                 | Directory where server logs are written.                                                                     |
| -logtofile     | false                | If true, logs are written only to file (no console output).                                                  |
| -sshport       | 2200                 | Port for the SSH server to listen on (reverse SSH feature).                                                  |
| -multiplexport | 2201                 | Port used by the SSH multiplexer endpoint for client apps.                                                   |

Scurid allows you to manage files on the device, including downloading, uploading, and deleting files. The file management APIs are designed to be simple and efficient, allowing you to interact with files on the device seamlessly.
Scurid Edge Agent will automatically download files from the server to the device, managed through a synchronization rate.

Following options allow you to manage the confiugration for the file management:

1. Automatic path creation (default is set to `false`): If the path does not exist, it will be created automatically. This will ensure that the file can be downloaded by the agent on a given path, even if that path does not exist. An error will be logged and visible in the App log, if the path cannot be created.
2. File Persistence (default is set to `false`): If set to `true`, the file will be persisted on the Server and agent will constantly synchronize the file with the server. If set to `false`, the file will be downloaded only once and not synchronized with the server.
3. Download path in agent (`required`): The path where the file will be downloaded on the agent. 
4. File location (`required`): The location of the file on the device from which files are being uploaded using the Scurid App.

!!! note "Current limitations"

    - Subfolders under the selected path are not supported. If they need to be transferred, they must be zipped before.
    - Empty files are not supported.


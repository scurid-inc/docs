# Release Notes


## August 2025

## General changes
* Improved reliability of file upload and download handling in unstable or persistence-off scenarios.  
* SSH usability improvements.  
* Various bugfixes and stability improvements.  

### Scurid App
* Added configuration option for SSH font size. 
* Fixed missing file paths for first file in upload sequence.

### Scurid Server
* Logging enhancements for file upload and download processes.
* Empty file path check, leading to server instability.

### Scurid Edge Agent 
* Resolved partial download issues in unstable networks with persistence off.  
* Fixed upload termination after network reconnection.  

## July 2025

## General changes
* Enhancements to file upload and download mechanisms across server and agents.  
* Improvements to SSH tunnel stability and authentication.  
* Various bugfixes and stability improvements.  

### Scurid App
* Fixed regression where starting SSH window crashed the app.  
* Fixed issue where update button was disabled despite valid paths.  
* Corrected agent total count display.  
* Fixed role visibility issue after creation.  
* Restored agent details visibility in About page.  

### Scurid Server
* Enhanced file upload process.  
* Removed dependency on GetAgentConfig in server-to-app logic.  

### Scurid Edge Agent
* Fixed regression in file download producing incorrect names.  
* Implemented temporary file download naming.  
* Ensured agentDownloadPath and userUploadPath are handled correctly per chunk.  
* Fixed issue preventing SSH tunnel start with username/password login.  

New releases will now be published on [Scurid Downloads](https://scurid.com/downloads) page.

## May 2025

## General changes
* Improved file transfer reliability across agents (download path, upload path, and duplicate download fixes).  
* Added visibility into agent heartbeat and last seen.  
* Various bugfixes and stability improvements.  

### Scurid App
* Fixed incorrect data shown for last seen across all agents.  
* Resolved Windows DLL crash causing failed uploads.  
* Fixed upload progress counter issue.  
* Investigation and fixes for high memory usage on Windows.  

### Scurid Server
* Improved GetAgentConfig error handling.  
* Enhanced file download logs with agent name.  
* Validation added to prevent illegal values in file paths.  

### Scurid Edge Agent
* Fixed issues with duplicate file downloads.  
* Ensured agentDownloadPath and userUploadPath are correctly handled per chunk.  

New releases will now be published on [Scurid Downloads](https://scurid.com/downloads) page.

## April 2025

## General changes
* Introduced file management across server and agent (upload, download, staging, and persistence).  
* Introduced secure and traceable file upload to agents.  
* Added SSH tunneling support between app, server, and edge agent (alpha).  
* Removed legacy `scurid_config` file and redefined onboarding process.  
* Various bugfixes and stability improvements.  

### Scurid App
* Added logging when user starts SSH.  
* Fixed invalid updates display.  
* Improved input validation for server and port.  
* Prevented API calls if required fields are empty during upload setup.  

### Scurid Server
* Enhanced file stage mechanism handling.  
* Updates received from edge when errors occur during downloads.  
* Input validation improvements.  
* Handling Codemagic build issues.  

### Scurid Edge Agent
* Added upload setting flags for file management.  
* Enhanced download mechanism with auto-directory creation.  
* Proper error handling when auto create folder is disabled.  
* Fixed table not found error when opening agent card.  
* Secure SSH key exchange with server for authentication.  

New releases will now be published on [Scurid Downloads](https://scurid.com/downloads) page.

## June 2024

## General changes 
* Implemented API for Device-to-User mapping.  
* Exposed device data via new APIs.  
* Various bugfixes and stability improvements.  

### Scurid App
* UI enhancement for User Access tab.  
* Fixed issues with logs, About page, and DB credentials display post-upgrade.  
* Prevented API calls without a valid token.  
* Fixed multiple onboarding errors and permission handling issues.  

### Scurid Server
* Fixed crashes on onboarding, upgrades, and duplicate invites.  
* Resolved server crashes and error handling for permission failures.  
* Bugfixes for role visibility, user role updates, and identity search with tags.  

### Scurid Edge Agent
* Fixed issues uploading data from edge to database.  

New releases will now be published on [Scurid Downloads](https://scurid.com/downloads) page.

## April 2024

## General changes
* Work started on internal eventing.  
* Introduced RBAC APIs with role creation and assignment.   
* Various bugfixes and stability improvements.  

### Scurid App
* Enhanced user invite flow with role info and passphrase enforcement.  
* UI/UX update to map users to devices.  
* Improved software update widget version handling.  
* Enabled Stripe self-account management.  

### Scurid Server
* Fixed multiple onboarding and installation panics (GetRoles, UpsertRole, RegisterAPI).  
* Added gRPC GetRoles and API authorization checks.  
* Enhanced TCP API for signature verification.  
* Server now pushes agent name to config for traceability.  

### Scurid Edge Agent
* Bugfixes in device identity handling and TLS connectivity.  
* Support for user-defined agent names and device_user association.

## October 29, 2023

## General changes
* Integrations across IoT and OT platforms like Hawkbit, PTC ThingWorx to automate identity and device onboarding. 
* Automated Azure IoT device certificate delivery to IoT devices running Edge Agent. 
* Enhanced user on-boarding process.
* Invite new users to join your organization.
* Email verification and password reset.
* Data collection and storage in Self-hosted CockroachDB.
* Bugfixes and performance improvements.
* Adoption of QBFT consensus algorithm in Scurid SSI.
* Performance monitoring *(in beta)*
* New releases will now be published on [Scurid Downloads](https://scurid.com/downloads) page.

### Scurid App
* Users can now configure agents to send data to self-hosted CockroachDB.
* Ability to change and enhance agent name.
* Create custom data structures for agents, by defining data structure in JSON format.
* Allow custom DB table creation and assignment to agents.
* Built-in reporting on data signing and verification on each agent.
* Simple pricing tiers, including free developer tier, available during sign-up.
* Invite new users to join your organization through simple user management.
* Release management widget to keep track of latest releases directly from the App.

### Scurid Server
* Promethues integration for performance monitoring
* Rate limiting on all gRPC API calls
* Region and connection handler for CockroachDB
* Built in email server for supporting new user invites

### Scurid Edge Agent
* Support for new data streaming APIs.
* Built in data signing and verification for each agent during data collection.
* New config.ymal file on the deivce to track agent configuration downloaded from the server. 


## December 11, 2022

## General changes
* Support for Microcontrollers esp. STM32, with launch of MicroScurid-C library
* Integration into CockroachDB for offering low code global storage for IoT/IIoT data
* Communication between Microcontroller and Scurid Server over protocol buffers
* Renaming Scurid backend to Scurid Server
* Each Scurid Server deployment to generate and manage its own server certificate

### Scurid App
* Select and create desired region for data storage
* Simplified flow to create database from the App
* Enhanced user on-boarding process to define data storage region
* Assign agents to data storage region

### Scurid Server
* Added TCP server to handle communication with Microcontrollers
* Several new internal APIs for subsystems, and data stream handling
* Region and connection handler for CockroachDB
* Database creation via CockroachDB
* Queries and batch management for data storage

### MicroScurid-C
* Create distributed identity (DID)
* Registration of identity with Scurid Server
* Setup TLS connection with Scurid Server


## August 15, 2022

## General changes

### Scurid Platform App
* Add helm pkg management for managed scurid backend #SPA-220
* Add platforminternal service to backend #SPA-188
* Update look and feel for Scurid Platform App #SPA-144
* Enable users to add or remove tags from the identities #SPA-99
* New Scurid Platform App and identity logging visibility

### Scurid Backend
* Logging APIs #SPA-230
* Enable authentication on Logging APIs #SPA-237
* Signed critical identity operations logs built-in #SPA-230
* SPA-243 Add licensing check

### Enhancement
* Remove the visit button SPA-200
* Rename DID to Device Identity on Identity card #SPA-222
* Make text on the app selectable #SPA-203
* Add auto approve identity setting #SPA-191
* Maintain path structures in post verify process on identities #SPA-139
* Enable path store in Approved identities #SPA-118
* Update client call in the gRPC dart for Scurid platform App #SPA-103
* Enable country search while on-boarding new user
* Make side menu collapsible #SPA-216

### Bug Fixes
* Pending identities do not show agent version #SPA-239
* List of related identities to an agent is missing #SPA-238
* For some identities, agent identity is missing #SPA-236
* Pending identities do not show context #SPA-234
* After approval card does not dismiss #SPA-233
* Bad state : No Element error #SPA-231
* Clean installation fails, unable to find subsystems #SPA-214
* A tag can be assigned to an identity multiple times #SPA-180
* Scurid backend crashes when staged folder is empty #SPA-179
* Inconsistent error popup #SPA-130
* Path display inconsistencies #SPA-129



## June 13, 2022

## General changes

### Scurid Platform App
* Enhanced UX with grid and table structure for Scurid Edge Agent and device identities
* Added identities count summary for each agent #SPA-206
* Users will now be able to reference agent identities with alias #SPA-202

### Scurid Backend
* Easy identifiable names for agents, when not defined by the user #SPA-209


## Bug Fixes

### Scurid Platform App
* Incorrect Scurid App binary name #SPA-212
* Fixed empty device context SPA-210
* Fixed Scurid Edge Agent name truncation during window resizing #SPA-201

### Scurid Backend
* Fixed issue with new installation unable to find Settings subsystem #SPA-214
* Fixed missing timestamp on Agent identity post reverification process SPA-204
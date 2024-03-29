# Release Notes

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
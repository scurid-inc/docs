Agent framework, as part of the core functionality, enables you to have your devices generate identity and reach out for identity workflow actions.

### Features
a. Simplifies tracking of all agents deployed in your IoT network
b. Extends device identity tracking not only to  each device but also to each agent
c. Capabilities to auto-approve an identity when coming from the trsuted agents, further simplifying the individual indentity worklfow

## Step 1 - Executing Scurid Edge Agent on IoT device
1. Run agent `./scuridedgeagent` 
   1. It exposes `-syncrate` flag `./scuridedgeagent -syncrate 90s`
   2. `-syncrate` defines how often the Edge agent will check for the pending agent's status with the Scurid backend
   3. Agent will start using `-syncrate` on agent startup, and continue to reference it until agent's status is confirmed
   4. Once completed agent will not use it any further, until restart of the agent, where steps 1.2 to 1.3 will be repeated
2. Post successful run of the agent, it will automatically set up `config.yaml` at location defined with the flag `-store` file with a new agent identity, if none created so far, and will attempt to contact the server passed to the agent using `-spaaddr` flag to inform the server about new agent's identity
3. Post user's review of the identity, depending on the decision (i.e. approved / revoked ) agent will download the approval key which will be appended to `config.yaml`

## Step 2 - Agent workflow via Scurid App or APIs

### Scurid App
todo : add screenshots

### Scurid backend's APIs
Backend exposes following set of Agent ID related workflow APIs under `PlatformAPIv2` 

#### Related APIs
1. `GetAgentsList` : Provides list of all the agent related identities on the backend server

2. `GetAgentInfo` : Provides an agent’s detailed information

3. `RegisterAgent` : Used  for approving a pending agent identity, Scurid SSI service call is wrapped within to appropriately handle data on the DLT managed under SSI

4. `RevokeAgent`: Revokes access for an agent, this is a global revocation of the agent’s identity, Scurid SSI service call is wrapped within to appropriately handle data on the DLT managed under SSI

5. `VerifyAgent` : Re-verifies an already approved agent identity,Scurid SSI service call is wrapped within to appropriately handle data on the DLT managed under SSI

### How is automatic Agent ID workflow handled by the Scurid backend and how to enable it?
1. After the Agent’s approval user will have to take a final step in the ID subsystem, which can be accessed via 
   1. App's UI : todo add UI flow here
   2. API endpoint group named `Subsystems` which contains two APIs
      1. `GetIDSettings` : Allows the caller to get currently configurable settings for the `Subsystem`
         1. `autoApproveDeviceID` which enables/disables auto-approve function for the device identities
         2. To offer full control to the users, this settings is set to `false` by default, i.e. users can decide to review each identity despite having an approved agent creating these identities.
      2. `SetIDSettings` : Allows the caller to set the desired state for configurable settings like `autoApproveDeviceID`
2. Once the agent is approved and for the time period `autoApproveDeviceID` is enabled - all upcoming new ID requests will be auto approved.
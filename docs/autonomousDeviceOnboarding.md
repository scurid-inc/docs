Agent framework, as part of the core functionality, enables you to have your devices generate identity and reach out for identity workflow actions.

## Features
1. Simplifies tracking of all agents deployed in your IoT network
2. Extends device identity tracking not only to  each device but also to each agent
3. Capabilities to auto-approve an identity when coming from the trsuted agents, further simplifying the individual identity workflow

## Step 1 - Executing Scurid Edge Agent on IoT device
1. Run agent `./scuridedgeagent` 
   1. It exposes `-syncrate` flag `./scuridedgeagent -syncrate 90s`
   2. `-syncrate` defines how often the Edge agent will check for the pending agent's status with the Scurid backend
   3. Agent will start using `-syncrate` on agent startup, and continue to reference it until agent's status is confirmed
   4. Once completed agent will not use it any further, until restart of the agent, where steps 1.2 to 1.3 will be repeated
2. Post successful run of the agent, it will automatically set up `config.yaml` at location defined with the flag `-store` file with a new agent identity, if none created so far, and will attempt to contact the server passed to the agent using `-spaaddr` flag to inform the server about new agent's identity
3. Post user's review of the identity, depending on the decision (i.e. approved / revoked ) agent will download the approval key which will be appended to `config.yaml`

## Step 2 - Agent workflow via Scurid App or APIs

Once the agent is installed and successfully run on an IoT hardware, it will send out onboarding request which can be reviewed either via `Scurid App` or `Scurid Backend's APIs`  

### Scurid App
1. Launch the app to review the pending agents ![pending agents](https://storage.cloud.google.com/scurid/public/docs/images/pendingagents.png){ width=800 }
2. Select the agent to review and approve. Notice along with the agent identity - it also sends out the related hardware details ![pending agents](https://storage.cloud.google.com/scurid/public/docs/images/pendingAgentDetails.png){ width=800 } 
3. Once approved, agent will be available for use via the approved list ![pending agents](https://storage.cloud.google.com/scurid/public/docs/images/approvedagent.png){ width=800 }


### Scurid backend's APIs
Backend exposes following set of Agent ID related workflow APIs under `PlatformAPIv2` which can be integered into your own IoT platform or Analytics platform 

#### Related APIs
1. `GetAgentsList` : Provides list of all the agent related identities on the backend server

2. `GetAgentInfo` : Provides an agent’s detailed information

3. `RegisterAgent` : Used  for approving a pending agent identity, Scurid SSI service call is wrapped within to appropriately handle data on the DLT managed under SSI

4. `RevokeAgent`: Revokes access for an agent, this is a global revocation of the agent’s identity, Scurid SSI service call is wrapped within to appropriately handle data on the DLT managed under SSI

5. `VerifyAgent` : Re-verifies an already approved agent identity,Scurid SSI service call is wrapped within to appropriately handle data on the DLT managed under SSI

## Automating device identity
With agent's setup successfully completed, you can now choose to enable automatic approval of device identities coming from the approved agent.
By default, this is disabled - requiring manual approval of the identities. 

To enable automatic identity approval, enable required configuration in the ID subsystem, which can be accessed via 
#### Option 1 : Enable via App's UI
1. Navigate to the `Settings` page ![general settings](https://storage.cloud.google.com/scurid/public/docs/images/generalsettings.png){ width=800 }
2. Switch to Identities and enable the `Auto Approve` setting ![id settings](https://storage.cloud.google.com/scurid/public/docs/images/identitiesAutoApproveOn.png){ width=800 } 

#### Option 2 : Enable via Backend APIs
1. API endpoint group named `Subsystems` which contains two APIs
2. `GetIDSettings` : Allows the caller to get currently configurable settings for the `Subsystem`
   1. `autoApproveDeviceID` which enables/disables auto-approve function for the device identities
   2. To offer full control to the users, this settings is set to `false` by default, i.e. users can decide to review each identity despite having an approved agent creating these identities.
   3. `SetIDSettings` : Allows the caller to set the desired state for configurable settings like `autoApproveDeviceID`

Once the agent is approved and for the time period `autoApproveDeviceID` is enabled - all upcoming new identities from the approved agents will be auto approved!
---
icon: paste
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# Copy to Clipboard

To support documentation each tab can be copy pasted as either Markown or plane text.

<figure><img src=".gitbook/assets/image (8).png" alt="" width="471"><figcaption></figcaption></figure>

Click the copy icon in the top right of the tab and the markdown/text will be added to your clipboard to paste into your documentation file (e.g Confluence or GitBook).

Example of a Markdown version of Solution tab

```
Solution
--------

### Details

Solution: Samples

UniqueName: Samples

Publisher: Sample

Version: 1.0.0.7

### Counts

Flows: 7

Environment Variables: 2

Connection References: 7

Tables: 7

Security Roles: 2

### Flows

| FlowName▲▼ | Trigger▲▼ | Actions▲▼ | Connections▲▼ | Variables▲▼ |
| --- | --- | --- | --- | --- |
| Pipeline Get Registry | Button | 12 | 1 | 0 |
| Pipeline Check Connections | Button | 16 | 3 | 1 |
| ar test | Button | 3 | 2 | 0 |
| ChildFlow A | Http | 2 | 1 | 0 |
| Pipeline Pre Export | When_an_action_is_performed | 20 | 2 | 0 |
| daTAFLOWS | Button | 1 | 1 | 0 |
| ai model | Button | 3 | 1 | 0 |

  

### Environment Variables

| VarName▲▼ | VarType▲▼ | VarSchema▲▼ | VarCon▲▼ | VarConType▲▼ | VarDefault▲▼ |
| --- | --- | --- | --- | --- | --- |
| Pipeline-RunPipeLine | String | ia_PipelineRunPipeLine |  |  |  |
| Environment | String | ia_Environment |  |  |  |

  

### Connection References

| ConName▲▼ | ConType▲▼ | ConSchema▲▼ |
| --- | --- | --- |
| crb89_agent.shared_commondataserviceforapps.c50b7a54db1f4858b3e3a8b6d9c7d702 | shared_commondataserviceforapps | crb89_agent.shared_commondataserviceforapps.c50b7a54db1f4858b3e3a8b6d9c7d702 |
| crb89_agent.shared_office365.0428413988c34d459c1dc3053d145356 | shared_office365 | crb89_agent.shared_office365.0428413988c34d459c1dc3053d145356 |
| AppAdmin-PipeLine | shared_powerappsforadmins | ia_AppAdminPipeLine |
| Dataverse-PipeLine | shared_commondataserviceforapps | ia_DataversePipeLine |
| Dataverse-SPN-PipeLine | shared_commondataserviceforapps | ia_DataverseSPNPipeLine |
| Power Query Dataflows Samples-3ccb9 | shared_dataflows | sample_shareddataflows_3ccb9 |
| Power Automate Management Samples-8b5b8 | shared_flowmanagement | yd_sharedflowmanagement_8b5b8 |

  

### Canvas Apps

| AppName▲▼ | AppSchema▲▼ | AppDescription▲▼ |
| --- | --- | --- |
|  |  |  |

  

### Copilto Studio Agents

| AgentName▲▼ | AgentSchema▲▼ | AppDeAgentTemplate▲▼ | AgentAuthMode▲▼ |
| --- | --- | --- | --- |
| Agent | crb89_agent | default-2.1.0 | 2 |

  

### Custom Connectors

| ConnectorName▲▼ | ConnectorDescription▲▼ | ConnectorHost▲▼ |
| --- | --- | --- |
| Default title | Returns an array of regex matches to input string | script.google.com |

  

### Dataverse Tables

| TableName▲▼ | TableSchema▲▼ |
| --- | --- |
| Deployment Register | cr4fe_DeploymentRegister |
| Service Accounts | cr4fe_ServiceAccounts |
| Dev Teams | cr4fe_Teams |
| Environment List | ia_EnvironmentList |
| Service Account Connections | ia_ServiceAccountConnections |
| SPN Connections | ia_SPNConnections |
| Exceptions | wd_Exceptions |

  

### Security Roles

| RoleName▲▼ | RoleSId▲▼ |
| --- | --- |
| Test Role | {03aff6af-ab28-ef11-840a-6045bd092a0d} |
| Test Security Role | {e3b91ba5-22a4-ef11-8a6a-6045bd09cc55} |

  

### Column Security Profiles

| ColumnName▲▼ | ColumnId▲▼ |
| --- | --- |
| Integrated Search Provider Profile |  |

  

### Missing Dependencies

| Required▲▼ | Type▲▼ | Depenendent▲▼ |
| --- | --- | --- |
| Connection Reference | 1 | Pipeline Check Connections |
| Flow Run | 1 | wd_EnvironmentExceptions |
| Status | 2 | wd_EnvironmentExceptions |
| AutoReview | 372 | ar test |
| AI Reply | 401 | ai model |
| msdyn_/Images/AppModule_Default_Icon.png | 61 | test model |
| msdyn_/Images/AppModule_Default_Icon.png | 61 | test web resource |
| Integrated Search Provider Profile | 70 | Integrated Search Provider Profile |
| Microsoft.PowerFx.Evaluator | 90 | wd_EnvironmentExceptions |
| ia_ApprovalsPipeline | connectionreference | Pipeline Pre Export |
| sample_sharedflowmanagement_ed298 | connectionreference | ar test |
| wd_AutoReview | connectionreference | ar test |
| wd_sharedsharepointonline_247f5__US | connectionreference | ChildFlow A |
| wd_system | connectionreference | ai model |
| AppChannel | SettingDefinition | parentappmoduleid.uniquename=sample_testmodel,settingdefinitionid.uniquename=AppChannel |
| AppChannel | SettingDefinition | parentappmoduleid.uniquename=sample_testwebresource,settingdefinitionid.uniquename=AppChannel |
```

{% hint style="info" %}
The setting to change from markdown to text is in the settings section in the about tab.
{% endhint %}

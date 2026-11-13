---
icon: box
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

# Solution

On the solution loading all of the key components are listed in tables.

<figure><img src="../.gitbook/assets/image (21).png" alt="" width="563"><figcaption></figcaption></figure>

Currently the following components are shown:

#### Flows

* FlowName
* Trigger
* Actions (count of)
* Connections (count of)
* Variables (count of)



#### Environment Variables

* VarName (display name)
* VarType
* VarSchema (unique name)
* VarCon (connection id SharePoint etc)
* VarConType (Site or List)
* VarDefault (if Default Value)



#### Connection References

* ConName (display name)
* ContTye (connection type e.g SharePoint)
* ConSchema (unique name)

#### Canvas Apps

* AppName (display name)
* AppSchema (unique name)
* AppDescription

#### Copilot Studio Agent

* AgentName (dsiplay name)
* AgentSchema (unique name)
* AgentTemplate
* AgentAuthMode&#x20;

#### Dataverse Tables

* TableName (display name)
* TableSchema (unique name)

#### Security Roles

* RoleName
* RoleSid (guid)

#### Column Security Profiles

* ColumnName
* ColumnId (guid)

#### Missing Dependencies&#xD;

* Required (name of dependency)
* Type&#x20;
* Dependent (component with the dependency)

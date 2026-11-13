---
icon: box
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
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

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

Solution covers the following following tables:

1. Missing Dependencies
2. Dataverse Tables
3. Environment Variables
4. Flows
5. Connection References



### Missing Dependencies

All missing dependencies are list showing the missing:

* Name - Component with the dependency
* Parent ID - Id of the component with the dependency e.g Flow id
* Type - Missing component type eg flow,connection reference, app
* Required - Unique name of missing component

_Sometimes the solution will show dependencies that are ok, like Custom Connectors, and standard tables, like Connection Reference table, just ignore these_



### Dataverse Tables

Any custom table included in the solution, showing display name, name, and description.



### Environment Variables

Shows all environment variables in the solution, AppReview-Pro only reads the variable definition, not any values (as these are environment specific.



* Name - Display name
* Description
* API - Any API's used (most do not have any)
* DataType&#x20;
* Type - DataType code

{% hint style="info" %}
The search box uses the following syntax (only filters Environment Variables)\
columnName = value\
columnName != value (not equal to)\
columnName includes value (in string)\
columnName !includes value (not n string)
{% endhint %}



### Flows

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

All flows within the solution are listed, this includes flows called by the App and standalone support flows.

* Name - Display name
* ID - Workflows (Process) table id
* SubProcess - Any child flows (0 No, 1 Yes)



### Connection References

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

Shows all connection references within the solution:

* Name - Display name
* ID - Unique name
* Type - Connection type e.g SharePoint

Type uses Microsoft's reference type, to translate this use the last part of the path

/providers/Microsoft.PowerApps/apis/shared\_**sharepoint**online = SharePoint

_Common data services is the legacy name for Dataverse_

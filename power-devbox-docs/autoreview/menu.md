---
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

# Menu

<figure><img src="../.gitbook/assets/image (181).png" alt="" width="348"><figcaption><p>Single Flow Solution</p></figcaption></figure>

Once a flow/solution has been selected the functions will open for the export. If a current flow or legacy export is selected then the solution (\*) functions will not show. &#x20;



If the solution has multiple flows the list will be shown, clicking on a flow from the Solution Contents section will select that flow. The selected from is shown above the Review function.

<figure><img src="../.gitbook/assets/image (96).png" alt="" width="362"><figcaption></figcaption></figure>

### Review

Loads the review file for the selected flow

### Report

Loads the report file for the selected flow. The report is similar to the review file but removes or grading/scoring of the flow, and is designed purely for documentation.

### Diagram

Loads a file with interactive graphical representation of the flow.

### Solution\*

Loads file with information about the contents of the solution uploaded.

### Compare With Previous

Compares 2 versions of a flow and lists the changes.

### Data

Loads the json object extracted from the flow, this is raw information that is used to create all files. See [data-json.md](data-json.md "mention")

### Definition

Loads the raw definition file from the flow. This definition is stored within the export and is just shown. See [https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json#](https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json) For more information there is a detailed Microsoft learn document: [https://learn.microsoft.com/en-us/azure/logic-apps/logic-apps-workflow-definition-language](https://learn.microsoft.com/en-us/azure/logic-apps/logic-apps-workflow-definition-language)

### Download Actions

Creates a csv file listing all actions from the flow and key information about each.

### Download Variables

Creates a csv file listing all variables from the flow and key information about each.

### Download Connections

Creates a csv file listing all connection references from the flow.

***



**Next Step - Files**

{% content-ref url="files/" %}
[files](files/)
{% endcontent-ref %}

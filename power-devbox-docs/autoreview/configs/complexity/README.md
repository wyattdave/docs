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

# Complexity

The Complexity is a value set to give higher weights to certain connectors. As certain connectors use more api calls or require higher technical understanding to debug.

_Negative values can be given, in default scopes are given negative values as they help make the flow more organised and easy to debug_

The connection information can be seen in the definition file, this information is then used in the config file.

**Example**

```json
 "type": "OpenApiConnection",
    "inputs": {
        "host": {
        "apiId": "/providers/Microsoft.PowerApps/apis/shared_excelonlinebusiness",
        "connectionName": "shared_excelonlinebusiness_1",
        "operationId": "GetItems"
        },
```

_The information above can be found in your flows definition file. AutoReview has an export definition feature so you can see your flows definition._

There are 3 levels to the scoring

#### 1. Action specific

If you have a particular action you want to score e.g. SharePoint get\_items, then you need to set the name as 'operationId' & 'connectionName' (this is because different connections share same operation e.g. bot excel and SharePoint have GetItems opertionId).

In the example you would set the name to 'GetItemsshared\_excelonelinebusiness' (the '\_1' should be ignored, as this is a reference to a connection reference as the example is in a solution).

_Action specific should be the top of the array, as AutoReview will pick the first found, and if its below a Type it will return the type complexity score instead._

#### 2. Type

All actions fall into a type category. The full list can be found her [Power Automate Schema](https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json)

So in the above example the name would be 'OpenApiConnection'

#### 3. Default

If a Action Specific value or Type cant be found a value of 1 will be given.



***

**Next Step - Naming Convention**

{% content-ref url="../naming-convention/" %}
[naming-convention](../naming-convention/)
{% endcontent-ref %}

**Additional Reading - Default values**

{% content-ref url="complexity-default-values.md" %}
[complexity-default-values.md](complexity-default-values.md)
{% endcontent-ref %}

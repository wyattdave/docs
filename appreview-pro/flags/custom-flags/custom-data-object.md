---
icon: list
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

# Custom Data Object

The custom data object converts all data within the solution to a JSON object that includes:

* AppConfig (data)
*  Solution (data)
* Code (text)
*  Screens (array/table of data)
*  ComponentTotals (array/table of data)
* Components (array/table of data)
* ComponentsYAML (array/table of data)
* Variables:
  * Local (array/table of data)
  * Global (array/table of data)
  * Formulas (text)
  * Collections (array/table of data)
*  Connections (array/table of data)
* DataSources (array/table of data)
* Flows (array/table of data)
* Tests
  * Suites (array/table of data)
  * Tests (array/table of data)
* MissingDependencies (array/table of data)
* EnvironmentVariables (array/table of data)
* ConnectionReferences (array/table of data)
* SolutionFlows (array/table of data)
* Tables (array/table of data)



The object is named **oData,** and the data can be referenced following standard dot notation.

Examples

```
oData.Varaibles.Global = table of variable
oData.Code = all Power FX code
oData.AppConfig.Name = App Name
```



{% content-ref url="../../exports/json-export-schema-odata.md" %}
[json-export-schema-odata.md](../../exports/json-export-schema-odata.md)
{% endcontent-ref %}

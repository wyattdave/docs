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

# Ratings Template

{% hint style="info" %}
When using in Power Automate Connector use the oRatingsTemplateas the input to Ratings (sReference can be ignored)
{% endhint %}



```json
{
  "sReference":"Replace with your reference",
  "oRatingsTemplate":{
    "complexityAm":50,
    "complexityRe":100,
    "actionsAm":30,
    "actionsRe":50,
    "variablesAm":3,
    "variablesRe":5,
    "exceptionsAm":1,
    "exceptionsRe":0
  }
}
```

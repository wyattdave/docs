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

# Naming Template

{% hint style="info" %}
When using in Power Automate Connector use the oNamingTemplate as the input to Naming (sReference can be ignored)
{% endhint %}



```json
{
  "oNamingTemplate": 
    {
      "sReference":"Replace with your reference",
      "char":1,
      "data": [
          { "Type": "boolean", "Letter": "b" }, 
          { "Type": "string", "Letter": "s" },
          { "Type": "integer","Letter": "i" },
          { "Type": "float", "Letter": "f" },
          { "Type": "object", "Letter": "o" },
          { "Type": "array", "Letter": "a" }
        ]
    }
}
```

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

# Naming Convention

The naming convention has 2 parts, number of lead characters and the type. It enforces camelcase, so it will always go 'typeVariableName'. The default it set to use first letter and that letter is just the first of type e.g

```json
"char":1
{ "Type": "string", "Letter": "s" },
```

\= sVariableName

```json
"char":2
{ "Type": "string", "Letter": "ss" },
```

\= ssVariableName

If a variable type is not found then the variable will pass, so if you don't want naming conventions you can leave the data array empty.



***

**Next Step - Ratings**

{% content-ref url="../ratings/" %}
[ratings](../ratings/)
{% endcontent-ref %}

**Additional Reading - Default values**

{% content-ref url="naming-convention-default-value.md" %}
[naming-convention-default-value.md](naming-convention-default-value.md)
{% endcontent-ref %}

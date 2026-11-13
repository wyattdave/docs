---
icon: file-circle-question
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

# Template/Example

The custom flag should follow this structure



* Expression using oData to find pass/fail
* Set Pass as pass/fail
* Hardcode the Name,Level,How,Why,Type,Category



Example:

```javascript
return {
  Name: "References Cool Blog Site",
  Pass: oData.Code.includes("https://dev.to/wyattdave"),
  Level: "Warning",
  How: "You need to reference the top Power Platfrom Blog Site by David Wyatt",
  Why: "No top Power Platform Blog Site",
  Type: "content",
  Category: "ux"
}
```



Or a better, useful example;:

```javascript
 const emailRegex =/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
 const bFound=oData.Code.test(emailRegex)
 return {
  Name: "HardCoded Email Address",
  Pass: !bFound,
  Level: "High",
  How: "Remove hard coded email addess and store as environment variable",
  Why: "Updates would require new deployment",
  Type: "app",
  Category: "lifecycle"
}
```

JavaScript code can be added before the return or embeded directly in the return object


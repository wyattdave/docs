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

# Scoring

Scoring is the split for the Overall Rating . Currently the colour grading is set to 0-74 Red, 75-89 Amber, 90+ Green, at present this can not be changed.

There are a few different scoring calculations, which currently cant be changed (the values can be changed, but the calculation formula cant). Each has a description to explain, some examples are

### Basic Score

```json
{
    "Name":"exceptionScope",
    "Score":10,
    "Note":"score added for exception scope"
}
```

If passes exception scope test scores 10 points

```json
    {
      "Name":"varConstant",
      "Score":5,
      "Note":"score added for naming variables with value in all capitals"
    }
```

If all variables with initialized variable name are all capitals then 5 points (e.g. sTIMESTAMP).

### **Threshold Score**

```json
    {
      "Name":"variables",
      "Score":10,
      "Note":"score given for variables before deductions"
    },
    {
      "Name":"variablesMin",
      "Score":0,
      "Note":"minimum allowed variables before deductions"
    },
    {
      "Name":"variablesDeduction",
      "Score":1,
      "Note":"score added for exception scope"
    }
```

For every variable above 0 deduct 1 point from 10 (will not go below 0).

### **Ratings Score**

```json
 {
    "Name":"complexityRed",
    "Score":0,
    "Note":"score added for red scoring complexity"
},
{
    "Name":"complexityAmber",
    "Score":15,
    "Note":"score added for amber scoring complexity"
},
{
    "Name":"complexityGreen",
    "Score":20,
    "Note":"score added green scoring complexity"
}
```

These are directly linked to the rating, so if complexity card was red 0 points, Amber 15 points, Green 20 points.

_There currently isn't a 100% validation so you can over score over 100 if you config it to do so._



***

**Further Reading - Default Values**

{% content-ref url="scoring-default-values.md" %}
[scoring-default-values.md](scoring-default-values.md)
{% endcontent-ref %}

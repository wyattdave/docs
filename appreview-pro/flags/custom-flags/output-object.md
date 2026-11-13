---
icon: right-from-bracket
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

# Output Object

All custom flags must return the same output JSON object, this object can then be used by AppReview-Pro to create the flag card.



* Name: Name of Flag (string)
* Pass: If passed flag (boolean)
* Level: Level of flag  (choice: High,Medium,Low,Warning)
* How: Changes made to pass flag (string)
* Why: Why it failed (string)
* Type: Area of fail (string, examples: app,screen,code)
* Category: Categorisation of flag (string, example: performance,accessability)





```javascript
return {
  Name: "{yourName}",
  Pass: {true,false},
  Level: "{High,Medium,Low,Warning}",
  How: "{yourFix}",
  Why: "{whyItFailed}",
  Type: "{app,screen,component,code}",
  Category: "{categoryOfFail e.g performance}"
}
```

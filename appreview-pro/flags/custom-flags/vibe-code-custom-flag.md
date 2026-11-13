---
icon: alien-8bit
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

# Vibe Code Custom Flag

With rise of AI tools and 'Vibing Coding' creating custom flags does not necessarily require JavaScript experience.

The prompt we recommend is:

***

Generate javascript code to do **\<what you want to do>** using below template:\
const i=oData.components.length;&#x20;\
return {\
&#x20; Name:"{yourName}",\
&#x20; Pass:{true,false},\
&#x20; Level:"{High,Medium,Low,Warning}",\
&#x20; How:"{yourFix}",\
&#x20; Why: "{whyItFailed}",\
&#x20; Type: ":{app,screen,component,code}",\
&#x20; Category:"{categoryOfFail e.g performance}"\
}\
where oData schema is:\
**\<add schema found here** [json-export-schema-odata.md](../../exports/json-export-schema-odata.md "mention")**>**

***

{% hint style="info" %}
Due to the token size of the schema not all free LLM will work, we have found Gemini free does so is our recommendation.
{% endhint %}

{% embed url="https://gemini.google.com/" %}




---
icon: arrow-right-from-bracket
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

All custom flags must have the same output object

<pre class="language-json"><code class="lang-json"><strong>{
</strong><strong>    area:"flow or solution",
</strong>    component:"action or component",
    type:"Readability",
    level:"Advice",
    reason:"This is a test, but in this case there is no notes in this action"
}
</code></pre>

The Output Object also has to returend as an array, a good example would be:

```json
let aErrors=[];
oData.flows.forEach(flow => {
  flow.review.actionArray.forEach(item =>{
    if(item.notes==""){
      aErrors.push({
        area:flow.review.name,
        component:item.name,
        type:"Readability",
        level:"Advice",
        reason:"This is a test, but in this case there is no notes in this action"
      })
    }
  })
})
return aErrors
}]
  
```

In this example the flag code:

* Loops over every flow
  * loops over every actionArray in the flow
    * If the action has no notes
    * Add the Output Object to the aErrors array
* Return the aErrors array



#### Headings

**Area:** Area of the exception/error, normally Solution for Environment Variables/Connection References, and the flow name for actions.

**Component:** Specific Environment Variable or action with the issue

**Type:** How you want to categorise the exception/error

**Level**: Error/Warning/Recommendation (though can be anything)

**Reason:** Reason for the failure

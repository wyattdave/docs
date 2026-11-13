---
icon: pen-ruler
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

# Flag Results

After the solution loads if there are Custom Flags and the solution fails some of them then there will be a Flag Results tab (note there is also a Flag Result for each flow, though this is a filtered view of this table).

<figure><img src="../.gitbook/assets/image (23).png" alt="" width="563"><figcaption></figcaption></figure>

The table will show the following columns:

* Flag - name of the custom flag
* Area - normally solution or the name of the flow
* Component - the action/component with the issue
* Type - your own categorisiation
* Level - Error, Warning, Comment (though you can add more)
* Reason - reason for failing



You can sort the table by clicking the arrows in each column header and use the quick filter for different levels.

<figure><img src="../.gitbook/assets/image (24).png" alt="" width="328"><figcaption></figcaption></figure>

{% hint style="info" %}
See [Settings](../settings.md) for extra functionality
{% endhint %}

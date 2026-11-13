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

# Compare with Previous

Once a flow is selected the Compare with Previous menu option will appear.

<figure><img src="../../.gitbook/assets/image (201).png" alt="" width="365"><figcaption></figcaption></figure>

Clicking the plus icon will add the flow as the second flow and turn the icon red

<figure><img src="../../.gitbook/assets/image (202).png" alt="" width="365"><figcaption></figcaption></figure>

Import the next version of the flow, select it, and then press the Compare with Previous option to open the Table version of the file.

### Table

<figure><img src="../../.gitbook/assets/image (117).png" alt=""><figcaption></figcaption></figure>

The Table will have the following fields:

| Field       | Description                                     | Example        |
| ----------- | ----------------------------------------------- | -------------- |
| Type        | Type of change, see Key                         | N              |
| Path        | JSON object that has the change                 | {"name"}       |
| First Flow  | Value of the flow selected with the plus icon   | \["Succeeded"] |
| Second Flow | Value of the flow selected with the menu option | \["Skipped"]   |

### Key

* N - indicates a newly added property/element&#x20;
* D - indicates a property/element was deleted&#x20;
* E - indicates a property/element was edited&#x20;
* A - indicates a change occurred within an array&#x20;

If N then First Flow will be blank, if D then Second flow will be blank

### Additional Functionality

#### JSON Schema

Json file representation of the changes.

* kind - indicates the kind of change; will be one of the following:
  * &#x20;kN - indicates a newly added property/element&#x20;
  * kD - indicates a property/element was deleted&#x20;
  * kE - indicates a property/element was edited&#x20;
  * kA - indicates a change occurred within an array&#x20;
* kpath - the property path (from the left-hand-side root)&#x20;
  * klhs - the value on the left-hand-side of the comparison (undefined if kind === "N")&#x20;
  * krhs - the value on the right-hand-side of the comparison (undefined if kind === "D")&#x20;
* kindex - when kind === "A", indicates the array index where the change occurred&#x20;
* kitem - when kind === "A", contains a nested change record indicating the change that occurred at the array index

<figure><img src="../../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

#### Download

Downloads a copy of the solution. When a solution is open it is linked to AutoReview so if saved through the browser all flow information will be lost. Downloading separates the solution and ensures the values are permanent.

#### Icon

Clicking the icon jumps back to the top of the page.



***

**Next Steps - CSV Files**

{% content-ref url="csv-files.md" %}
[csv-files.md](csv-files.md)
{% endcontent-ref %}

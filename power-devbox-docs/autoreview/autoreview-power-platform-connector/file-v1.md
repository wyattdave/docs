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

# File (v1)

### Inputs (required)

<figure><img src="../../.gitbook/assets/image (86).png" alt="" width="563"><figcaption></figcaption></figure>

#### Display Name

Display name of the flow

#### Flow ID

Unique ID of the flow, recommend using Resource id or workflowid

#### Owner

Flow owner/maker

#### Environment

Environment name

#### Definition

Flow definition/clientData

### Inputs Optional

AutoReview allows configuration of the review metrics,  if left blank the review will follow the default values.

<figure><img src="../../.gitbook/assets/image (87).png" alt="" width="491"><figcaption></figcaption></figure>

* [complexity](../configs/complexity/ "mention")
* [naming-convention](../configs/naming-convention/ "mention")
* [ratings](../configs/ratings/ "mention")
* [scoring](../configs/scoring/ "mention")

#### Complexity

New complexity items can be added with the 'Add new item' button. Though we recommend using the text mode (small pen in top right corner).



<figure><img src="../../.gitbook/assets/image (150).png" alt="" width="185"><figcaption><p>Use text mode for easier editing</p></figcaption></figure>

The [complexity json](../configs/complexity/complexity-template.md) object can then be edited in a source code editor (like Visual Studio Code or Notepad++) and then pasted in its entirety into the aComplexityTemplate input. With the reference inputted to the Reference Complexity.

<figure><img src="../../.gitbook/assets/image (89).png" alt="" width="439"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (92).png" alt="" width="433"><figcaption></figcaption></figure>

#### Naming Convention

The [naming convention json](../configs/naming-convention/naming-template.md) has to be placed in 3 inputs.

<figure><img src="../../.gitbook/assets/image (91).png" alt="" width="442"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (93).png" alt="" width="435"><figcaption></figcaption></figure>

* Naming Reference - sReference
* Naming Char - char
* data - data array

#### Ratings

Each [rating key](../configs/ratings/ratings-template.md) needs to be entered into the relevant inputs.

<figure><img src="../../.gitbook/assets/image (151).png" alt="" width="563"><figcaption></figcaption></figure>

#### Scoring

The [scoring json](../configs/scoring/scoring-template.md) follows same pattern as complexity, with the reference input separately from the aScoringTemplate array.

<figure><img src="../../.gitbook/assets/image (90).png" alt="" width="444"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (94).png" alt="" width="437"><figcaption></figcaption></figure>

### Outputs

The File api returns the following

* File
* Data

#### File

The file key returns a HTML pile that can be used to create a file. There are 4 different file types:

* [review.md](../files/review.md "mention")
* [report.md](../files/report.md "mention")\*
* [diagram.md](../files/diagram.md "mention")\*
* [exceptions.md](../files/exceptions.md "mention")\*\*

_\*coming soon \*\*coming not so soon_

#### Data

Data is a stringified json and once parsed returns different values depending on the file selected.

#### Review and Report

| Key          | Description                                  | Example |
| ------------ | -------------------------------------------- | ------- |
| Complexity\* | Complexity score                             | 100     |
| Actions      | Count of all actions                         | 40      |
| Variables    | Count of variables                           | 4       |
| Exceptions   | Count of exception actions (runAfter Failed) | 2       |
| Connections  | Count of connections                         | 2       |
| Premium      | Uses premium actions                         | true    |

_\*Review only_

#### **Diagram**

Returns the [nomnoml](https://www.nomnoml.com) file. This file is similar to mermaid and creates a text file that is rendered as a diagram. The text can be pasted into nomnoml site or a site using the library.

```
#fillArrows: true
#lineWidth: 2
#fill:#569AE5
#background: white
#acyclicer: greedy
#ranker: tight-tree
#.data: visual=database fill=#EBDAF9
#.trigger: visual=roundrect fill=#569AE5
#.if: visual=rhomb fill=#2596be
#.switch: visual=ellipse fill=#2596be
#.scope: visual=frame fill=#808080
#.foreach: visual=transceiver fill=#00C1A0
#.until: visual=sender fill=#00C1A0
#.var: visual=input fill=#9925be
#.terminate: visual=receiver fill=#cc4747
#.var: visual=input fill=#EBDAF9

[<trigger> *Recurrence]->[HTTP]
[<foreach>Apply_to_each]--:>[<terminate>Terminate]
[HTTP]->[<data>Parse_JSON]
[<data>Parse_JSON]->[<foreach>Apply_to_each]
```

<figure><img src="../../.gitbook/assets/image (157).png" alt=""><figcaption></figcaption></figure>



***

**Next Steps - Files**

{% content-ref url="../files/" %}
[files](../files/)
{% endcontent-ref %}




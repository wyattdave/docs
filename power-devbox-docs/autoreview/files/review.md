---
description: >-
  The Review file combines scoring of the flow and key information for you to
  view
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

# Review

{% embed url="https://wyattdave.github.io/Auto-Review/Auto-Review%20Demos/Review%20test.html" %}
Live Demo of a Review file
{% endembed %}

The Review file has 10 sections

* Meta Data
* Score Cards
* Overall Score
* Trigger\*
* Variable's\*
* Actions\*
* Action Inputs\*
* API Actions\*
* Connection References\*

_(\*) Same sections used in Report file, to see more information please_ [report.md](report.md "mention")

### &#x20;Meta Data

Basic information about the flow, including flow name, flow id, owner and date review ran.

### Score Cards

<figure><img src="../../.gitbook/assets/image (165).png" alt=""><figcaption></figcaption></figure>

Shows the points for the following metrics. The cards works on a Red, Amber, Green rating, with the thresholds set through the Ratings config file. You can configure your own values through the [configs](../configs/ "mention") files.

{% content-ref url="../configs/ratings/ratings-default-value.md" %}
[ratings-default-value.md](../configs/ratings/ratings-default-value.md)
{% endcontent-ref %}

#### **Complexity**

A metric that focuses on the type of connection used, as an example a flow using http actions and loops will be classified as more complex then a similar length flow with a Get Items and filter action. Each actions complexity value is set through the Complexity config file.

{% content-ref url="../configs/complexity/complexity-default-values.md" %}
[complexity-default-values.md](../configs/complexity/complexity-default-values.md)
{% endcontent-ref %}

_Default Thresholds_

| Green | Amber | Red   |
| ----- | ----- | ----- |
| <50   | 50-99 | >=100 |

#### **Actions**

Raw count of actions within the flow.

_Default Thresholds_

| Green | Amber | Red  |
| ----- | ----- | ---- |
| <30   | 30-49 | >=50 |

#### Variables

Raw count of variables used within the flow.

_Default Thresholds_

| Green | Amber | Red |
| ----- | ----- | --- |
| <3    | 3/4   | >=5 |

#### Exceptions

Count of actions using Run After 'Failed'.

_Default Thresholds_

| Green | Amber | Red |
| ----- | ----- | --- |
| >1    | 1     | 0   |

### Overall Score

<figure><img src="../../.gitbook/assets/image (166).png" alt="" width="563"><figcaption></figcaption></figure>

The Overall score includes a flow score out of 100 and additional flags.

#### Flow Score

The Flow score is the sum of metrics from the flow. Like all can be scoring, you can set your own values through the [configs](../configs/ "mention") files, in particular the Score Config file.

{% content-ref url="../configs/scoring/scoring-default-values.md" %}
[scoring-default-values.md](../configs/scoring/scoring-default-values.md)
{% endcontent-ref %}

_Enforced Thresholds_

| Green | Amber | Red |
| ----- | ----- | --- |
| >=90  | 89-75 | <75 |

#### Variables

Flag to show if all variables meet the following requirements:

1. Follows naming convention
2. Is used within the flow

#### Composes

Count of Composes used in the flow. This value is also used in the Overall Score.

#### Main

Is a root scope used called 'Main' to enable a single Run After 'Failed' to catch all exceptions. This value is also used in the Overall Score.

#### Exception

Is a root scope used called 'Exception' with Run After set to 'Failed', to catch all exceptions from the 'Main' scope. This value is also used in the Overall Score.



***

### Top Bar

The top bar has some additional functionality:

#### Review Configs

<figure><img src="../../.gitbook/assets/image (170).png" alt="" width="563"><figcaption></figcaption></figure>

The current configs will show, 'default' shows that no custom configs have been set. This allows context for the review score and enable version control.

* Com: Complexity
* Rat: Ratings
* Nam: Naming Convention
* Sco: Score

#### Download

Downloads a copy of the review. When a review is open it is linked to AutoReview so if saved through the browser all flow information will be lost. Downloading separates the review and ensures the values are permanent.

#### Icon

Clicking the icon jumps back to the top of the page.

***

**Next Steps - Remaining sections**

{% content-ref url="report.md" %}
[report.md](report.md)
{% endcontent-ref %}


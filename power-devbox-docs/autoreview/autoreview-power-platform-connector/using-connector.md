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

# Using Connector

The connector can be used in 2 main ways.

### Dataverse

For all solution aware flows the Dataverse 'Get a row by id' or by 'List rows'. To use the list rows the action must be set to the Process (workflows) table and have a filter set to:

```
category eq 5
```

As this filters out business rules, desktop flows, and other workflows that are not compatible. Using the expand and select on createdby can also be used to get the flow owners name.

ClientData is generally stored as a string so will need to be converted to a json (wrap in json() expression).

<figure><img src="../../.gitbook/assets/image (241).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
Please ensure you do not over your daily API limit else you will be throttled and may have you key cancelled (use row count to limit)
{% endhint %}



### My Flows

You can also use the Power Automate Management connectors. This will cover all flows, including non solution aware, but is limited to your flows so can not be used by admins to view all flows.

<figure><img src="../../.gitbook/assets/image (242).png" alt="" width="563"><figcaption></figcaption></figure>

The 'List My Flows' lists all flows, the 'Get Flow' is then used to get the flow definition for AutoReview (currently the 'Get Flow as Admin' does not return the definition).

The flow name is passed as the Flow ID (not the display name)

{% hint style="info" %}
Please ensure you do not over your daily API limit else you will be throttled and may have you key cancelled
{% endhint %}


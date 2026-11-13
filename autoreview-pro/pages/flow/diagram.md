---
icon: share-nodes
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

# Diagram

The Diagram tab shows a visual representation of the flow. It does not follow the Power Automate UI exactly.

To show the tab click the link at the top of the Flow Review tab:

<figure><img src="../../.gitbook/assets/image (33).png" alt="" width="563"><figcaption></figcaption></figure>

The Diagram will open in its own tab and show the flow.

<figure><img src="../../.gitbook/assets/image (27).png" alt="" width="563"><figcaption></figcaption></figure>

Dotted lines show the continuation of the flow run after the container. So in the above example:

Inside the Main scope is:

* List\_rows
* Condition
* Condition\_PreDeploy
* List\_rows\_environments

After Main scope is the Exception Scope

Inside Condition is:

* Respond\_to\_a\_PowerApp\_or\_flow\_missing
* Terminate

After Condition is 2 branches, List\_rows\_environments and Condition\_PreDeploy



Hovering over a action will show breadcrumbs of any nesting.

<figure><img src="../../.gitbook/assets/image (28).png" alt="" width="538"><figcaption></figcaption></figure>

Clicking ona action will open the side panel with information about that action.

<figure><img src="../../.gitbook/assets/image (29).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
The Copy to Clipboard icon will add the svg code to your clipboard
{% endhint %}

{% hint style="info" %}
Icons often use the provided url from Power Automate, so these may not work offline
{% endhint %}

#### Custom Flags

The "Highlight Flagged Items on Diagram" option in [settings](../../settings.md) can be used to highlight flagged actions.

<figure><img src="../../.gitbook/assets/image (30).png" alt="" width="563"><figcaption></figcaption></figure>

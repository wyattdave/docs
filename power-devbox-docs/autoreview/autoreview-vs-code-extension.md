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

# AutoReview - VS Code Extension

The VS code extension allows you to extract key information from any open definition.json flow files.

### Open File

The extenion requires a open json file. First export your solution as a zip. Extract the zip file and navigate to the workflows folder.

<figure><img src="../.gitbook/assets/image (65).png" alt="" width="563"><figcaption></figcaption></figure>

Open any flow JSON Source File with VS Code. Press ctrl+p to open the command palette.

<figure><img src="../.gitbook/assets/image (67).png" alt="" width="563"><figcaption></figcaption></figure>

### Commands

**Flow Details:** Opens up a quick popup message in the bottom right with number of actions, trigger type, and if it is premium

<figure><img src="../.gitbook/assets/image (68).png" alt="" width="549"><figcaption></figcaption></figure>

**Flow Review:** Opens to json file with all of the flow details (schema: [data-json.md](data-json.md "mention"))

<figure><img src="../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The VS Code data json has an additional field:  **environmentCount.** This shows the number of environment variables in the avtion, useful for SharePoint actions to ensure both site and list are envirnoment variables.
{% endhint %}

**Flow Actions:** Json array of all actions within the flow.

<figure><img src="../.gitbook/assets/image (70).png" alt="" width="563"><figcaption></figcaption></figure>

**Flow Connections:** Json array of all connections within the flow.

<figure><img src="../.gitbook/assets/image (71).png" alt="" width="563"><figcaption></figcaption></figure>

**Flow Diagram:** Svg diagram of the flow.

<figure><img src="../.gitbook/assets/image (73).png" alt="" width="563"><figcaption></figcaption></figure>


---
icon: file-arrow-up
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

# Export/Import Custom Flags

Custom Flags can be export and imported between AppReview-Pro instances.

To export the custom flags click the Export Custom Flags button.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

A simple json object will be created and download. Please note the custom code is stored as a string. The live key allows the flag to be skipped, so if you don't want all custom flags, after downloading edit the live to false and it will not upload.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

To upload the custom flag export us the same Choose Export button used for uploadding solution zip / app msapp files.&#x20;

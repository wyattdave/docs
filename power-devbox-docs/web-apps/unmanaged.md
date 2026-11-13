---
icon: box-open-full
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

# Unmanaged

Solutions can be exported as either managed or unmanaged. Managed are read only versions, so when imported they can not be edit.

{% embed url="https://unmanaged.powerdevbox.com/" %}

Unmanaged allows you to convert managed solutions to unmanaged when the developer version has been lost.

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>



Simply drag the managed solution onto the drag and drop rectangle or click to upload and select the export.

The unmanaged version will then be automatically downloaded to your download file.

### How It Works

Solutions contain mulitple files, including a solution.xml file. This file has a \<managed> tag, when set to 0 it is unmanaged, 1 is managed. Unmanaged simply changes it from 1 to 0. You can do it yourself without unmanaged by:

* Copy solution.xml our of zip
* Edit and Save the file
* Copy back into the zip file


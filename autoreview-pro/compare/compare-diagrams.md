---
icon: display
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

# Compare Diagrams

By clicking on a Flow from the Compare Table a new window will open showing both the new and older flow diagram.

<figure><img src="../.gitbook/assets/image (37).png" alt="" width="563"><figcaption></figcaption></figure>

The new version will appear on the left and the old on the left. Each action will be colour coded depending on any changes

<figure><img src="../.gitbook/assets/image (38).png" alt="" width="128"><figcaption></figcaption></figure>



Due to how the data is stored in Power Automate we are limited by how we can track changes, so we will show:

* Same - no change
* Modified - changes to inputs, settings, runAfter
* Renamed - name change
* Deleted - either removed from flow or Modified and Renamed



Clicking on a action will open a popup window with the 2 versions of the actions information side by side to compare.

<figure><img src="../.gitbook/assets/image (39).png" alt="" width="563"><figcaption></figcaption></figure>

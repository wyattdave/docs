---
icon: code-compare
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

# Compare Table

AutoReview-Pro allows you to compare versions of solutions (currently only compares flows, not other solution components).

To compare 2 versions of the same solution, first import the latest version, then input the older version. Instead of opening the older version the Compare table will load.

<figure><img src="../.gitbook/assets/image (1).png" alt="" width="563"><figcaption></figcaption></figure>

Please note all of interactions with AutoReview-Pro will still show the newest version.



The table will list all flows from the new version (deleted flows from the older version are currently not shown). Each flow will have a Status of either Same,Modified, or New Flow.

The table also lists the current counts of:

* New Actions
* Modified Actions
* Renamed Actions
* Same Actions
* Deleted Actions



Due to how the data is stored in Power Automate we are limited by how we can track changes, so we will show:

* Same - no change
* Modified - changes to inputs, settings, runAfter
* Renamed - name change
* Deleted - either removed from flow or Modified and Renamed









Cl

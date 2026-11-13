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

# Diagram

{% embed url="https://wyattdave.github.io/Auto-Review/Auto-Review%20Demos/Diagram%20test.html" %}
Live demo of Diagram file
{% endembed %}

The diagram file creates a visual representation of the flow.

<figure><img src="../../.gitbook/assets/image (158).png" alt=""><figcaption></figcaption></figure>

The diagram can be zoomed in and out by dragging the top slider.

### Key

Each action type is represented on diagram by a different shape/colour, this information can be found on the key (Click key icon on the left bar).

<figure><img src="../../.gitbook/assets/image (159).png" alt=""><figcaption><p>Key</p></figcaption></figure>

<table><thead><tr><th>Type</th><th>Colour</th><th width="242">Shape</th><th>Container</th></tr></thead><tbody><tr><td>Trigger</td><td>Blue</td><td>Pill</td><td>False</td></tr><tr><td>API based action</td><td>Blue</td><td>Rectangle</td><td>False</td></tr><tr><td>Data Operator</td><td>Pink</td><td>Parallelogram</td><td>False</td></tr><tr><td>Branch Logic</td><td>Turquoise</td><td>Oval / Diamond</td><td>True</td></tr><tr><td>Loop</td><td>Green</td><td>Arrow / Arrow Head</td><td>True</td></tr><tr><td>Scope</td><td>Grey</td><td>Rectangle with Tab</td><td>True</td></tr><tr><td>Terminate</td><td>Red</td><td>Arrow End</td><td>False</td></tr></tbody></table>



To show progress within containers a standard line connects the contents, a dotted line connects the action after the container.

### Popups

<figure><img src="../../.gitbook/assets/image (160).png" alt=""><figcaption></figcaption></figure>

Clicking on each action withing the diagram will show a popup with key information about the action.

* Name
* ID - operationMetadataId from definition, note not all actions have a operationMetadataId
* Type - type of action, unlike other files this does not replace OpenApiConnections with the operationId
* Step - operationId from definition
* Index - unique reference generated sequentially from the definition, in other files known as Id
* Detail - all inputs
* Tier - standard or premium license required to use
* Filter - any query's for GetItems
* Pagination - if Pagination is turned on shows row limit
* Retry - if none default retry policy shows the policy
* Timeout - retry timeout
* Notes - notes added to action (not comments), only shows if has a note

### Side Header

<figure><img src="../../.gitbook/assets/image (161).png" alt="" width="370"><figcaption></figcaption></figure>

The side bar has 3 main buttons:

#### Save SVG (down arrow)

Saves a copy of the diagram as svg (loses interactive functionality i.e. popups).

#### Key

Shows the key with explanation for all actions.

#### Download

Downloads a copy of the diagram file. When a review is open it is linked to AutoReview so if saved through the browser all flow information will be lost. Downloading separates the diagram and ensures the values are permanent.

***

**Next Step - Exceptions**

{% content-ref url="exceptions.md" %}
[exceptions.md](exceptions.md)
{% endcontent-ref %}

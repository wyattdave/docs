---
icon: folder-magnifying-glass
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

# Solution Explorer

Solution Explorer gies a visual representation of the key components of a Power Platform solution

{% embed url="https://solution.powerdevbox.com" %}

1. How to load
2. Views
3. Components
4. Links
5. Filters
6. Export

***

### 1. How to load

To load drag the solution onto the drag and drop rectangle or click to upload and select the export.

<figure><img src="../.gitbook/assets/image (285).png" alt="" width="563"><figcaption></figcaption></figure>

The solution will load as a linked diagram, with components referenced linked.

<figure><img src="../.gitbook/assets/image (286).png" alt="" width="563"><figcaption></figcaption></figure>

In the example above you can see what connection references are used in each flow, what flows are called as child flows, and which environment variable is used in a agent.

### 2. Views

There are 2 views to show components that can be set by clicking the hamburger menu and toggling diagram mode.

<figure><img src="../.gitbook/assets/image (288).png" alt="" width="563"><figcaption></figcaption></figure>

#### Diagram Mode

Shows components and links that represent the use of other components

<figure><img src="../.gitbook/assets/image (287).png" alt="" width="563"><figcaption></figcaption></figure>

The above shows that the Get Registry flow is called by the Pre Export flow and uses the Environment list table and Dataverse-PipeLine connection reference.

#### List Mode

List mode groups all components by type and lists them.

<figure><img src="../.gitbook/assets/image (289).png" alt="" width="563"><figcaption></figcaption></figure>

### 3. Components

The following components are supported:

<table><thead><tr><th width="136.3333740234375">Icon</th><th>Component</th><th>Relationships</th></tr></thead><tbody><tr><td><img src="../.gitbook/assets/powerAutomate.png" alt=""></td><td>Flows</td><td>Connection Reference, Environment Variables, Apps, Agents, Tables, Functions</td></tr><tr><td><img src="../.gitbook/assets/powerApps.png" alt=""></td><td>Canvas Apps</td><td>Connection Reference, Environment Variables, Tables, Functions</td></tr><tr><td><img src="../.gitbook/assets/powerAppsModel.png" alt=""></td><td>Model Driven Apps</td><td>Connection Reference, Environment Variables, Tables</td></tr><tr><td><img src="../.gitbook/assets/agent.png" alt=""></td><td>Copilot Studio Agent</td><td>Connection Reference, Environment Variables, Flows, Tables</td></tr><tr><td><img src="../.gitbook/assets/connectors.png" alt=""></td><td>Connection References</td><td>Flows, Canvas Apps, Model Driven Apps, Copilot Studio Agent, Custom Connectors</td></tr><tr><td><img src="../.gitbook/assets/enviVarIcon.png" alt=""></td><td>Environment Variable</td><td>Flows, Canvas Apps, Model Driven Apps, Copilot Studio Agent</td></tr><tr><td><img src="../.gitbook/assets/custom.png" alt=""></td><td>Custom Connector (shows connector icon)</td><td>Connection References</td></tr><tr><td><img src="../.gitbook/assets/powerFx.png" alt=""></td><td>Dataverse Functions</td><td>Flows, Canvas Apps</td></tr><tr><td><img src="../.gitbook/assets/secure white.png" alt=""></td><td>Security Role</td><td></td></tr><tr><td><img src="../.gitbook/assets/image (11).png" alt="" data-size="original"></td><td>Ai Builder Models</td><td>Flows, Canvas Apps</td></tr><tr><td><img src="../.gitbook/assets/image (12).png" alt="" data-size="original"></td><td>Dataflows</td><td>Flows</td></tr><tr><td><img src="../.gitbook/assets/image (10).png" alt="" data-size="original"></td><td>Web Resources</td><td></td></tr><tr><td> <img src="../.gitbook/assets/image (296).png" alt=""></td><td>Missing Dependencies (off by default)</td><td>Every Component</td></tr></tbody></table>





### 4. Links

To improve visibility of relationships link lines can be clicked to highlight them in red.

<figure><img src="../.gitbook/assets/image (290).png" alt="" width="563"><figcaption></figcaption></figure>

Click again to remove the highlighting. Multiple lines can be highlighted at once.



### 5. Filters

Solution Explorer includes 2 types of filters, component and flow name.

<figure><img src="../.gitbook/assets/image (291).png" alt="" width="374"><figcaption></figcaption></figure>

#### Component

Remove the checkbox against a component will remove it from the diagram.

<figure><img src="../.gitbook/assets/image (292).png" alt="" width="563"><figcaption></figcaption></figure>

#### Flow

The flows can be filtered by contains word or doesnt contain word. Adding a word will filter flows so that only flows with the matching text will show in the diagram

<figure><img src="../.gitbook/assets/image (293).png" alt="" width="563"><figcaption></figcaption></figure>

A not contains filter is also availble, with the ! prefix. So in this case it will only show flows that do not contain the text in the display name.

<figure><img src="../.gitbook/assets/image (294).png" alt="" width="563"><figcaption></figcaption></figure>

### 6. Export

There are 3 types of exports.

* SVG
* PNG
* CSV



<figure><img src="../.gitbook/assets/image (295).png" alt="" width="347"><figcaption></figcaption></figure>

SVG exports the diagram as a SVG, this is a vector image so can be scaled (zoomed in/out) without losing resolution (SVGs are not compatible with some image software, but are with web browsers).



PNG are standard image exports, you can download in 3 sizes, Low (1024 pixels wide), Medium (2048 pixels wide), and High (4094 pixels wide).&#x20;



CSV creates a table of all the components by name, id(or unique name) and type.&#x20;

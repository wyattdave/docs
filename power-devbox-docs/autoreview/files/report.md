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

# Report

The Report file extracts key information from the flow to support documentation.

{% embed url="https://wyattdave.github.io/Auto-Review/Auto-Review%20Demos/Report%20test.html" %}
Live Demo of a Report file
{% endembed %}

The Report file has 8 sections

* Meta Data
* Trigger
* Variable's
* Actions
* Action Inputs
* API Actions
* Connection References

_All sections are also used in Report file_



All table sections include filters and notes.

<figure><img src="../../.gitbook/assets/image (169).png" alt="" width="238"><figcaption></figcaption></figure>

Filters are set by column/field and then by Filter value. The filter works on a 'contains' match logic, not exact (e.g. 'tag' would return 'stag' and 'tagging').

Notes are by default hidden, clicking on the title will show the free text input. This value will only be saved if the report is printed or downloaded

### Meta Data

Basic information about the flow, including flow name, flow id, owner and date review ran.

### Trigger

<figure><img src="../../.gitbook/assets/image (167).png" alt=""><figcaption></figcaption></figure>

Displays trigger information from the flow, some information is dependent on type. The following headings are included:

#### Type

* Manual - Button, App, Bot
* Recurrence - Scheduled
* Automatic - This will show type of trigger action

#### Parameters

All inputs to the trigger including non configurable ones, shown as a JSON object.

#### Configuration

Additional settings not covered by standard settings, shown as a JSON object.

#### Inputs

Any inputs to the trigger, shown as a JSON object.

#### Recurrence

Settings for recurring flows, shown as a JSON object.

#### Expressions

Trigger conditions, shown as a JSON object.



### Variables

<figure><img src="../../.gitbook/assets/image (168).png" alt=""><figcaption></figcaption></figure>

List of variables in the flow, showing key information:

* Name
* Type - string, integer, boolean, array, object
* Value - input of the variable
* Used - used within the flow
* Named - follows naming convention
* Constant - meets constant convention - set value name should be all capitals except for leading type characters.

### Actions

<figure><img src="../../.gitbook/assets/image (171).png" alt=""><figcaption></figcaption></figure>

All actions are listed, with:

* Name
* Type - standard actions like Conditions (If) have their own type, all other actions (OpenApiConnection) don't, so the operationId is used instead (e.g.GetItems)
* Run After - what action and condition runs after
* Notes - notes added to action (not comments), the cell can be extended for readability by dragging bottom right triangle
* Nested - actions that it is nested in (using Id), as example '3|2' means it is inside action 3 which is inside action 2 (so a nesting level of 2)
* Id - unique reference used for nesting, generated sequentially from the definition.

Each actions name is a hyperlink to the same action in the Actions Inputs Table.

### Actions Inputs

<figure><img src="../../.gitbook/assets/image (172).png" alt=""><figcaption></figcaption></figure>

All actions are listed, with:

* Name
* Type - standard actions like Conditions (If) have their own type, all other actions (OpenApiConnection) don't, so the operationId is used instead (e.g.GetItems)
* Env - contains an environment variable within an input
* Inputs - all inputs to the action in JSON format, the cell can be extended for readability by dragging bottom right triangle

Each actions name is a hyperlink to the same action in either the Actions Table (if not an api action like a compose) of the API Actions Table.

### API Actions

<figure><img src="../../.gitbook/assets/image (173).png" alt=""><figcaption></figcaption></figure>

Only actions that are non standard and are classified as OpenApiConnection are listed, with:

* Name
* Type - operationId
* Connector - connection used
* Filter - any query's for GetItems
* Pagination - If Pagination is turned on shows row limit
* Retry - if none default retry policy shows the policy

Warning triangle's show when a GetItem type action does not have both a filter and pagination turned on.

Each actions name is a hyperlink to the same action in the Actions Table .

### Exceptions

<figure><img src="../../.gitbook/assets/image (174).png" alt=""><figcaption></figcaption></figure>

Lists any actions that are set to run after 'Failed', with:

* Action - type
* Name
* Runafter - action it runs after and all conditions

### Connection References

<figure><img src="../../.gitbook/assets/image (175).png" alt=""><figcaption></figcaption></figure>

Lists all connection references used, with:

* Name - connection name within the flow (duplicates with show with trailing \_1 or other numbers)
* Id - connection type
* Count - how many actions use the connection reference



***

### Top Bar

The top bar has some additional functionality:

#### Download

Downloads a copy of the review. When a review is open it is linked to AutoReview so if saved through the browser all flow information will be lost. Downloading separates the report and ensures the values are permanent.

#### Icon

Clicking the icon jumps back to the top of the page.



***

**Next Step - Diagram**

{% content-ref url="diagram.md" %}
[diagram.md](diagram.md)
{% endcontent-ref %}

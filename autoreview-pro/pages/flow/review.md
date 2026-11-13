---
icon: file-magnifying-glass
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

# Review

<figure><img src="../../.gitbook/assets/image (26).png" alt="" width="563"><figcaption></figcaption></figure>

The Flow Review tab is the main tab in AutoReview-Pro, it extracts all the key information from the flow and shows it in a clear and accessible way.

At the top is the key information, covering name, counts and the Trigger information.

There are 6 tables of data, all of which can be sorted and filtered.

#### Connections

Lists all connections used within the flow

* Connection (name of connection in flow)
* CoRef (name of connection reference)
* CoType (type of connection e.g SharePoint)
* RunAs (embed or run only)
* CoUsed (count used)

#### Action Inputs

All actions focused on settings

* Name (action name)
* Env (count of environment variables in input)
* Secure (if useing securing inputs/outputs)
* Inputs (input json)

#### Actions Overview

All actions focused on information about the action

* Name (action name)
* Type&#x20;
* RunAfter
* Notes
* Index (unique number of action)
* Nested (all of actions nested in - uses Index)

#### API Actions\#

All actions that call external systems e.g. SharePoint/Outlook/Dataverse

* Name
* Connector (connector type e.g SharePoint)
* Connecton (from connection table)
* Type (Interaction type e.g ListRecords for Get items)
* Retry&#x20;
* Timeout
* Filter (ListRecords only)
* Pagination (ListRecords only)

#### Variables

All variables initialised in the flow.

* VaName
* VaType
* Value
* Used (count of used outside of initialise,set,append,increment,etc)
* Set (count of initialise,set,append,increment,etc)

#### Exceptions

All actions that have runAfter set to Failed

* ExName (action name)
* ExType (action type e.g. Compose)
* RunAfter

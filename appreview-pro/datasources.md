---
icon: database
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
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

# Datasources

Data sources cover connections based on data links, examples include SharePoint and Dataverse.

<figure><img src=".gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

The table covers

* Name
* Source
* Count Used



Dataverse Source will show default.cds.

Datasources do not declare if they are a environment variable anywhere in the file, these means a custom rule was required. The rule is that if the Name of the Datasource is the same as the schema name. ie.&#x20;

_List called **Responders**, Datasource name **Responders** = **Not environment variable**_

_List called **Responders**, Datasource name **Responder-list** = **Environment variable**_

Please keep this in mind when reviewing apps.

{% hint style="info" %}
The search box uses the following syntax

**columnName = value**

**columnName != value (not equal to)**

**columnName includes value (in string)**

**columnName !includes value (not n string)**
{% endhint %}




---
icon: tags
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

# Variables

Variables covers 4 pages:

1. Local
2. Global
3. Formulas
4. Collections



### 1. Local

Local are all local variables scoped to a screen, ie variables set with updateContext({}).

The table covers

* Variable (name)
* Screen (screen local to)
* Count Set (how often value set)
* Count Used (how often referenced)

As local can be repeated the variable may appear multiple time, but only ever once per screen



### 2. Global

<figure><img src=".gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

Global are all variables used across the app, ie variables set with Set().

The table covers

* Variable (Name)
* Type (always global)
* Count Set (how often value set)
* Count Used (how often referenced)

{% hint style="info" %}
Power FX is not type safe (ie variable are not declared with a type like string) and currently there is no schema within the app, this has made it very difficult to identify the type (this is why we have a repurposed type column), we are still working on trying to achieve this
{% endhint %}



### 3. Formulas

Formulas covers the Formula parameter on the app (this was a preview feature so maybe missed from some legacy exports).

It covers both variables declared and UDF (user defined functions), due to the flexibility of how this is used the code is shown with no transformation.



### 4. Collections

Collections are arrays/tables of data stored locally in the app. Collections were stored i nthe data sources file in a solution and had a schema, this has recently changed and they have become untyped like variables.

The table only shows:

* Name
* Count Used

<figure><img src=".gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
The search box uses the following syntax

**columnName = value**

**columnName != value (not equal to)**

**columnName includes value (in string)**

**columnName !includes value (not n string)**
{% endhint %}

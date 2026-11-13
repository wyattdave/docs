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

# AutoReview - Power Platform Connector

{% embed url="https://learn.microsoft.com/en-us/connectors/autoreview/" %}

### Authentication

The connector requires a api key which can be requested here [https://powerdevbox.com/contact.html](https://powerdevbox.com/contact.html), we endeavour to provide free api keys for all users, but infrastructure may limit the number available.



### Actions

There are 5 actions included with the connector (and one legacy version).

<figure><img src="../../.gitbook/assets/image (217).png" alt="" width="563"><figcaption></figcaption></figure>

### Info

<figure><img src="../../.gitbook/assets/image (218).png" alt="" width="563"><figcaption></figcaption></figure>

Provides latest updates and version information about the connector. This also includes your account details, like api key expiry and daily/monthly usage.

<figure><img src="../../.gitbook/assets/image (219).png" alt="" width="563"><figcaption></figcaption></figure>

{% content-ref url="info-v1-and-v2.md" %}
[info-v1-and-v2.md](info-v1-and-v2.md)
{% endcontent-ref %}

***

### JSON

JSON returns a json object covering key information about the flow

<figure><img src="../../.gitbook/assets/image (220).png" alt="" width="563"><figcaption></figcaption></figure>



{% content-ref url="json-v1-and-v2.md" %}
[json-v1-and-v2.md](json-v1-and-v2.md)
{% endcontent-ref %}

***

### File

Creates a HTML output of all key information and scores.

<figure><img src="../../.gitbook/assets/image (221).png" alt="" width="563"><figcaption></figcaption></figure>

{% content-ref url="file-v2.md" %}
[file-v2.md](file-v2.md)
{% endcontent-ref %}

***



**Next Steps -  Using Connector**

{% content-ref url="using-connector.md" %}
[using-connector.md](using-connector.md)
{% endcontent-ref %}



**Further Reading -  Files**

{% content-ref url="../files/" %}
[files](../files/)
{% endcontent-ref %}

**Further Reading - API Connector Built On**

{% content-ref url="../api/" %}
[api](../api/)
{% endcontent-ref %}

---
icon: clipboard-list
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

# Test Custom Flag

During your creation of custom flags you can run tests to validate if they are working as expected.

By default there is a saved solution export built into AppReview-Pro, this built in solution is like a test file that should have all data to test. To see the test file click the Download to JSON option in the settings cog.

{% content-ref url="../../exports/" %}
[exports](../../exports/)
{% endcontent-ref %}

If you load your own export then this will be used for all testing.

To test click the Text Custom Flags button.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

This will show all of the custom flags with their output data and the card that would appear.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Unlike in the Flags section of a review, all flags are shown, even ones that pass.



### Sensitization

For security certain JavaScript functions are not allowed within a custom flag.

If you enter a function that is banned it will be sanitized with ¬¬¬¬¬¬¬¬



<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
Please note if a flag fails validation/is sanitized then it will not save. AppReview-Pro will also check the flag at run time and will skip it if it fails (but will notify you).
{% endhint %}

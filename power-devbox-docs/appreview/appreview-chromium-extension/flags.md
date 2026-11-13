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

# Flags

Flags use the built in App Checker and some additional checks to flag code review issues.

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

### Additional Checks

* Solution - All Applications should now be exported as solutions<i class="fa-fw">:fw:</i>
* Environment Variables - Environment variables should be used for all datasource
* Missing Dependencies
* Screens - If over 10 screens impacts performance and maintenance of app. Reuse screens or split into 2 apps.true
* Connections - Over 5 connections shows over complexity and may flag as a security concern
* Components Per Screen - Over 400 will impact performance of the screen
* Concurrent - Concurrent should be used to improve performance
* Filter of Filter - Filter(Filter( will have poor performance and should use And/Or conditions
* Iferror - Error handling should be used for external actions












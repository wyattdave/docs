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

# Solution

The Solution file shows key information about the solution.

<figure><img src="../../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure>

It covers:

* Name
* Version&#x20;
* Publisher
* Connection References
* Environment Variables
* Missing Dependencies



### Metadata

The file will show the solution name, its current version number and the publisher.

### Connection References

All connection references will be listed and include:

| Field        | Description                  | Example             |
| ------------ | ---------------------------- | ------------------- |
| Name         | Display name                 | SharePoint Test App |
| Type         | Connection type id,          | shared\_sharepoint  |
| id           | Unique name of the reference | SharePointTestApp   |
| Customizable | Enables solution layers      | true                |

### Environment Variables

List of environment variables, this is based on the definitions table so does not show any values.&#x20;

| Field        | Description                                                | Example      |
| ------------ | ---------------------------------------------------------- | ------------ |
| Name         | Unique name of the variable definition  (not display name) | testApp-site |
| Type         | Variable type, see below table                             | 100000000    |
| Customizable | Enables solution layers                                    | true         |



| Values    | Label       |
| --------- | ----------- |
| 100000000 | String      |
| 100000001 | Number      |
| 100000002 | Boolean     |
| 100000003 | JSON        |
| 100000004 | Data Source |
| 100000005 | Secret      |

### Missing Dependencies

List of any missing dependencies that could cause the solution to fail to import unless they are already imported.

<figure><img src="../../.gitbook/assets/image (115).png" alt=""><figcaption></figcaption></figure>

| Field     | Description                                            | Example             |
| --------- | ------------------------------------------------------ | ------------------- |
| Name      | unique name of the component (not always display name) | testApp-site        |
| Type      | Component type                                         | connectionreference |
| Dependent | Component with dependency                              | Your flow name      |



### Additional Functionality

#### JSON Schema

Json file representation of the customizations.xml file from inside the solution export

<figure><img src="../../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>

#### Download

Downloads a copy of the solution. When a solution is open it is linked to AutoReview so if saved through the browser all flow information will be lost. Downloading separates the solution and ensures the values are permanent.

#### Icon

Clicking the icon jumps back to the top of the page.



***

**Next Step - Compare With Previous**

{% content-ref url="compare-with-previous.md" %}
[compare-with-previous.md](compare-with-previous.md)
{% endcontent-ref %}

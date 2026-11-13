---
icon: list
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

# Custom Data Object

The Custom Flags allow you to write JavaScript to read the solution and create flags/exceptions.

<figure><img src="../.gitbook/assets/image (40).png" alt="" width="563"><figcaption></figcaption></figure>

Key to this is the Custom Data Object, which is used in the custom flags.

* connectionReferences
* tables
* securityProfile
* canvasApps
* customControls
* roles
* languageCode\*
* connectors
* dependencies
* displayName\*
* name\*
* version\*
* publisher\*
* environmentVariables
* flows
* agents



\*All other items are arrays

```json
{
  "$schema": "http://autoreview-pro.dev/schema/solution/schema.json",
  "title": "Power Platform Solution Metadata",
  "type": "object",
  "properties": {
    "displayName": { "type": "string" },
    "name": { "type": "string" },
    "version": { "type": "string" },
    "publisher": { "type": "string" },
    "languageCode": { "type": "integer" },
    "connectionReferences": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "connectionreferencelogicalname": { "type": "string" },
          "connectionreferencedisplayname": { "type": "string" },
          "connectorid": { "type": "string" },
          "iscustomizable": { "type": "integer" },
          "statecode": { "type": "integer" },
          "statuscode": { "type": "integer" },
          "type": { "type": "string" }
        },
        "required": ["connectionreferencelogicalname", "connectorid"]
      }
    },
    "environmentVariables": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "displayName": { "type": "string" },
          "name": { "type": "string" },
          "type": { "type": "integer" },
          "displayType": { "type": "string" }
        }
      }
    },
    "flows": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "displayName": { "type": "string" },
          "id": { "type": "string" },
          "review": {
            "type": "object",
            "properties": {
              "trigger": { "type": "object" },
              "actionArray": {
                "type": "array",
                "items": {
                  "type": "object",
                  "properties": {
                    "name": { "type": "string" },
                    "step": { "type": "string" },
                    "type": { "type": "string" },
                    "runAfter": { "type": "string" }
                  }
                }
              },
              "variableArray": { "type": "array" }
            }
          }
        }
      }
    },
    "dependencies": { "type": "array" },
    "tables": { "type": "array" },
    "canvasApps": { "type": "array" }
  },
  "required": ["name", "version", "connectionReferences", "flows"]
}
```

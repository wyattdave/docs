---
icon: square-code
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

# Definition

The Definition file is the main JSON of the flow, where all of the flows information is stored.

To show the tab click the link at the top of the Flow Review tab:

<figure><img src="../../.gitbook/assets/image (36).png" alt="" width="563"><figcaption></figcaption></figure>

The definition JSON follows Microsoft's schema: [https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json#](https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json), it is used by AutoReview-Pro to complete the reviews. The structure is not designed to be easily read (this is why the JSON is converted into the [Data ](data.md)JSON)

An example would be:

```json
Schema:[https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json#](https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json#)

{
  "properties": {
    "connectionReferences": {
      "shared\_commondataserviceforapps\_1": {
        "runtimeSource": "embedded",
        "connection": {
          "connectionReferenceLogicalName": "ia\_DataversePipeLine"
        },
        "api": {
          "name": "shared\_commondataserviceforapps"
        }
      }
    },
    "definition": {
      "$schema": "https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json#",
      "contentVersion": "1.0.0.0",
      "parameters": {
        "$connections": {
          "defaultValue": {},
          "type": "Object"
        },
        "$authentication": {
          "defaultValue": {},
          "type": "SecureObject"
        }
      },
      "triggers": {
        "manual": {
          "metadata": {
            "operationMetadataId": "0458c648-f808-4e6b-8cef-1b31127553fd"
          },
          "type": "Request",
          "kind": "Button",
          "inputs": {
            "schema": {
              "type": "object",
              "properties": {
                "text": {
                  "title": "solutionName",
                  "type": "string",
                  "x-ms-dynamically-added": true,
                  "description": "Please enter your input",
                  "x-ms-content-hint": "TEXT"
                },
                "number": {
                  "title": "TypeNumber",
                  "type": "number",
                  "x-ms-dynamically-added": true,
                  "description": "Please enter a number",
                  "x-ms-content-hint": "NUMBER"
                },
                "boolean": {
                  "title": "PreDeploy",
                  "type": "boolean",
                  "x-ms-dynamically-added": true,
                  "description": "Please select yes or no",
                  "x-ms-content-hint": "BOOLEAN"
                }
              },
              "required": \[
                "text",
                "number",
                "boolean"
              \]
            }
          }
        }
      },
      "actions": {
        "Respond\_to\_a\_PowerApp\_or\_flow": {
          "runAfter": {
            "Main": \[
              "Succeeded"
            \]
          },
          "metadata": {
            "operationMetadataId": "2ca75d92-d07c-4fd1-b614-4fab098d5998"
          },
          "type": "Response",
          "kind": "PowerApp",
          "inputs": {
            "statusCode": 200,
            "body": {
              "displayname": "@{outputs('List\_rows')?\['body/value'\]\[0\]?\['cr4fe\_solutiondisplayname'\]}",
              "serviceaccount": "@{if(equals(triggerBody()\['number'\],1),outputs('List\_rows')?\['body/value'\]\[0\]?\['cr4fe\_prodserviceaccount'\],outputs('List\_rows')?\['body/value'\]\[0\]?\['cr4fe\_testserviceaccount'\])}",
              "teamname": "@{outputs('List\_rows')?\['body/value'\]\[0\]?\['cr4fe\_\_teams/cr4fe\_teamname'\]}",
              "teamsecuirtygroup": "@{outputs('List\_rows')?\['body/value'\]\[0\]?\['cr4fe\_\_teams/cr4fe\_securitygroup'\]}",
              "flows": "@{outputs('List\_rows')?\['body/value'\]\[0\]?\['cr4fe\_flowson'\]}",
              "environmenturl": "@{if(triggerBody()\['boolean'\],outputs('List\_rows\_environments\_Dev')?\['body/value'\]\[0\]?\['ia\_url'\],outputs('List\_rows\_environments')?\['body/value'\]\[0\]?\['ia\_url'\])}",
              "environmentid": "@{outputs('List\_rows\_environments')?\['body/value'\]\[0\]?\['ia\_id'\]}"
            },
            "schema": {
              "type": "object",
              "properties": {
                "displayname": {
                  "title": "displayName",
                  "x-ms-dynamically-added": true,
                  "type": "string"
                },
                "serviceaccount": {
                  "title": "serviceAccount",
                  "x-ms-dynamically-added": true,
                  "type": "string"
                },
                "teamname": {
                  "title": "teamName",
                  "x-ms-dynamically-added": true,
                  "type": "string"
                },
                "teamsecuirtygroup": {
                  "title": "teamSecuirtyGroup",
                  "x-ms-dynamically-added": true,
                  "type": "string"
                },
                "flows": {
                  "title": "flows",
                  "x-ms-dynamically-added": true,
                  "type": "boolean"
                },
                "environmenturl": {
                  "title": "environmentUrl",
                  "x-ms-dynamically-added": true,
                  "type": "string"
                },
                "environmentid": {
                  "title": "environmentId",
                  "x-ms-dynamically-added": true,
                  "type": "string"
                }
              }
            }
          },
          "description": "If PreDeploy return Dev environment url instead of target"
        },
        "Main": {
          "actions": {
            "List\_rows": {
              "runAfter": {},
              "metadata": {
                "operationMetadataId": "5291d5f1-861c-44e5-beb1-4a5f052c7a18"
              },
              "type": "OpenApiConnection",
              "inputs": {
                "host": {
                  "connectionName": "shared\_commondataserviceforapps\_1",
                  "operationId": "ListRecords",
                  "apiId": "/providers/Microsoft.PowerApps/apis/shared\_commondataserviceforapps"
                },
                "parameters": {
                  "entityName": "cr4fe\_deploymentregisters",
                  "$filter": "cr4fe\_solutionname eq '@{triggerBody()\['text'\]}'",
                  "$expand": "cr4fe\_\_teams"
                },
                "authentication": {
                  "type": "Raw",
                  "value": "@json(decodeBase64(triggerOutputs().headers\['X-MS-APIM-Tokens'\]))\['$ConnectionKey'\]"
                }
              }
            },
            "Condition": {
              "actions": {
                "Respond\_to\_a\_PowerApp\_or\_flow\_missing": {
                  "runAfter": {},
                  "metadata": {
                    "operationMetadataId": "2ca75d92-d07c-4fd1-b614-4fab098d5998"
                  },
                  "type": "Response",
                  "kind": "PowerApp",
                  "inputs": {
                    "statusCode": 200,
                    "body": {
                      "displayname": "$not registered$"
                    },
                    "schema": {
                      "type": "object",
                      "properties": {
                        "displayname": {
                          "title": "displayName",
                          "x-ms-dynamically-added": true,
                          "type": "string"
                        },
                        "serviceaccount": {
                          "title": "serviceAccount",
                          "x-ms-dynamically-added": true,
                          "type": "string"
                        },
                        "teamname": {
                          "title": "teamName",
                          "x-ms-dynamically-added": true,
                          "type": "string"
                        },
                        "teamsecuirtygroup": {
                          "title": "teamSecuirtyGroup",
                          "x-ms-dynamically-added": true,
                          "type": "string"
                        },
                        "flows": {
                          "title": "flows",
                          "x-ms-dynamically-added": true,
                          "type": "boolean"
                        },
                        "environmenturl": {
                          "title": "environmentUrl",
                          "x-ms-dynamically-added": true,
                          "type": "string"
                        },
                        "environmentid": {
                          "title": "environmentId",
                          "x-ms-dynamically-added": true,
                          "type": "string"
                        }
                      }
                    }
                  }
                },
                "Terminate": {
                  "runAfter": {
                    "Respond\_to\_a\_PowerApp\_or\_flow\_missing": \[
                      "Succeeded"
                    \]
                  },
                  "metadata": {
                    "operationMetadataId": "e7648e33-c066-46f8-a541-166568ee1f05"
                  },
                  "type": "Terminate",
                  "inputs": {
                    "runStatus": "Succeeded"
                  }
                }
              },
              "runAfter": {
                "List\_rows": \[
                  "Succeeded"
                \]
              },
              "expression": {
                "equals": \[
                  "@empty(outputs('List\_rows')?\['body/value'\])",
                  "@true"
                \]
              },
              "metadata": {
                "operationMetadataId": "55d772ea-7bf6-4044-8018-c26720ec9787"
              },
              "type": "If"
            },
            "List\_rows\_environments": {
              "runAfter": {
                "Condition": \[
                  "Succeeded"
                \]
              },
              "metadata": {
                "operationMetadataId": "6f9666c1-0993-42df-ba21-5eb9255603d4"
              },
              "type": "OpenApiConnection",
              "inputs": {
                "host": {
                  "connectionName": "shared\_commondataserviceforapps\_1",
                  "operationId": "ListRecords",
                  "apiId": "/providers/Microsoft.PowerApps/apis/shared\_commondataserviceforapps"
                },
                "parameters": {
                  "entityName": "ia\_environmentlists",
                  "$filter": "ia\_geo eq @{outputs('List\_rows')?\['body/value'\]\[0\]?\['ia\_geo'\]} and ia\_environmenttype eq @{triggerBody()\['number'\]}"
                },
                "authentication": {
                  "type": "Raw",
                  "value": "@json(decodeBase64(triggerOutputs().headers\['X-MS-APIM-Tokens'\]))\['$ConnectionKey'\]"
                }
              }
            },
            "Condition\_PreDelploy": {
              "actions": {
                "List\_rows\_environments\_Dev": {
                  "runAfter": {},
                  "metadata": {
                    "operationMetadataId": "6f9666c1-0993-42df-ba21-5eb9255603d4"
                  },
                  "type": "OpenApiConnection",
                  "inputs": {
                    "host": {
                      "connectionName": "shared\_commondataserviceforapps\_1",
                      "operationId": "ListRecords",
                      "apiId": "/providers/Microsoft.PowerApps/apis/shared\_commondataserviceforapps"
                    },
                    "parameters": {
                      "entityName": "ia\_environmentlists",
                      "$filter": "ia\_geo eq @{outputs('List\_rows')?\['body/value'\]\[0\]?\['ia\_geo'\]} and ia\_environmenttype eq 3"
                    },
                    "authentication": {
                      "type": "Raw",
                      "value": "@json(decodeBase64(triggerOutputs().headers\['X-MS-APIM-Tokens'\]))\['$ConnectionKey'\]"
                    }
                  }
                }
              },
              "runAfter": {
                "Condition": \[
                  "Succeeded"
                \]
              },
              "expression": {
                "equals": \[
                  "@triggerBody()\['boolean'\]",
                  "@true"
                \]
              },
              "metadata": {
                "operationMetadataId": "9f70611e-2466-4e07-b658-85f514173629"
              },
              "type": "If"
            }
          },
          "runAfter": {},
          "metadata": {
            "operationMetadataId": "213293b1-040c-4eed-b086-779a405264da"
          },
          "type": "Scope"
        },
        "Exception": {
          "actions": {
            "Filter\_array": {
              "runAfter": {},
              "metadata": {
                "operationMetadataId": "32010288-ee22-4799-a898-299cd9b1d69e"
              },
              "type": "Query",
              "inputs": {
                "from": "@result('Main')",
                "where": "@equals(item()\['status'\], 'Failed')"
              }
            },
            "Respond\_to\_a\_PowerApp\_or\_flow\_exception": {
              "runAfter": {
                "Filter\_array": \[
                  "Succeeded"
                \]
              },
              "metadata": {
                "operationMetadataId": "2ca75d92-d07c-4fd1-b614-4fab098d5998"
              },
              "type": "Response",
              "kind": "PowerApp",
              "inputs": {
                "statusCode": 200,
                "body": {
                  "displayname": "$not registered$",
                  "serviceaccount": "@{coalesce(body('Filter\_array')\[0\]?\['outputs'\]?\['body'\]?\['error'\]?\['innerError'\]?\['error'\]?\['message'\], body('Filter\_array')\[0\]?\['outputs'\]?\['body'\]?\['error'\]?\['message'\])\\r\\n}"
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "displayname": {
                      "title": "displayName",
                      "x-ms-dynamically-added": true,
                      "type": "string"
                    },
                    "serviceaccount": {
                      "title": "serviceAccount",
                      "x-ms-dynamically-added": true,
                      "type": "string"
                    },
                    "teamname": {
                      "title": "teamName",
                      "x-ms-dynamically-added": true,
                      "type": "string"
                    },
                    "teamsecuirtygroup": {
                      "title": "teamSecuirtyGroup",
                      "x-ms-dynamically-added": true,
                      "type": "string"
                    },
                    "flows": {
                      "title": "flows",
                      "x-ms-dynamically-added": true,
                      "type": "boolean"
                    },
                    "environmenturl": {
                      "title": "environmentUrl",
                      "x-ms-dynamically-added": true,
                      "type": "string"
                    },
                    "environmentid": {
                      "title": "environmentId",
                      "x-ms-dynamically-added": true,
                      "type": "string"
                    }
                  }
                }
              },
              "description": "If PreDeploy return Dev environment id instead of taerget"
            }
          },
          "runAfter": {
            "Main": \[
              "Failed",
              "TimedOut"
            \]
          },
          "metadata": {
            "operationMetadataId": "6b69e46d-3a82-4b81-b943-1ccba5b2f6e7"
          },
          "type": "Scope"
        }
      }
    },
    "templateName": ""
  },
  "schemaVersion": "1.0.0.0"
}
```

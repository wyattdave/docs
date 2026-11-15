# Solution Download

Solutions can be exported and imported to new instances of Flow Utilizer. The export is a YAML file, with the schema below.

{% hint style="info" %}
The YAML file can be edited and re-imported, but be aware that it must still be a compliant YAML file (with below schema), and any incorrect calculations will be corrected on import
{% endhint %}

### YAML Schema

```yaml
$schema: "http://json-schema.org/draft-07/schema#"
type: object
properties:
  solutionName:
    type: string
  solutionId:
    type: string
    format: uuid
  flows:
    type: array
    items:
      type: object
      properties:
        flowId:
          type: string
        name:
          type: string
        dailyCalls:
          type: string
          pattern: "^[0-9]+$"
        runCalls:
          type: string
          pattern: "^[0-9]+$"
        actions:
          type: integer
        dailyRuns:
          type: string
          pattern: "^[0-9]+$"
        solution:
          type: string
        on:
          type: boolean
        containers:
          type: array
          items:
            type: object
            properties:
              type:
                type: string
                enum:
                  - action
                  - loop
                  - condition
              name:
                type: string
              id:
                type: string
              iterations:
                type: [number, "null"]
              parent:
                type: string
              actions:
                type: integer
              totalCalls:
                type: number
              branch:
                type: string
                enum:
                  - y
                  - n
              flow:
                type: string
              level:
                type: integer
              dailyCalls:
                type: [number, "null"]
            required:
              - type
              - name
              - id
              - actions
              - totalCalls
              - flow
              - level
        daysOfWeek:
          type: string
          pattern: "^(su|mo|tu|we|th|fr|sa)(\\|su|\\|mo|\\|tu|\\|we|\\|th|\\|fr|\\|sa)*$"
        totalCalls:
          type: number
      required:
        - flowId
        - name
        - dailyCalls
        - runCalls
        - actions
        - dailyRuns
        - solution
        - on
        - containers
        - daysOfWeek
        - totalCalls
  dailyCalls:
    type: string
    pattern: "^[0-9]+$"
  modified:
    type: string
    pattern: "^\\d{2}/\\d{2} - \\d{2}:\\d{2}$"
required:
  - solutionName
  - solutionId
  - flows
  - dailyCalls
  - modified
```

### JSON Schema

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "properties": {
    "solutionName": {
      "type": "string"
    },
    "solutionId": {
      "type": "string",
      "format": "uuid"
    },
    "flows": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "flowId": {
            "type": "string"
          },
          "name": {
            "type": "string"
          },
          "dailyCalls": {
            "type": "string",
            "pattern": "^[0-9]+$"
          },
          "runCalls": {
            "type": "string",
            "pattern": "^[0-9]+$"
          },
          "actions": {
            "type": "integer"
          },
          "dailyRuns": {
            "type": "string",
            "pattern": "^[0-9]+$"
          },
          "solution": {
            "type": "string"
          },
          "on": {
            "type": "boolean"
          },
          "containers": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "type": {
                  "type": "string",
                  "enum": ["action", "loop", "condition"]
                },
                "name": {
                  "type": "string"
                },
                "id": {
                  "type": "string"
                },
                "iterations": {
                  "type": ["number", "null"]
                },
                "parent": {
                  "type": "string"
                },
                "actions": {
                  "type": "integer"
                },
                "totalCalls": {
                  "type": "number"
                },
                "branch": {
                  "type": "string",
                  "enum": ["y", "n"]
                },
                "flow": {
                  "type": "string"
                },
                "level": {
                  "type": "integer"
                },
                "dailyCalls": {
                  "type": ["number", "null"]
                }
              },
              "required": ["type", "name", "id", "actions", "totalCalls", "flow", "level"]
            }
          },
          "daysOfWeek": {
            "type": "string",
            "pattern": "^(su|mo|tu|we|th|fr|sa)(\\|su|\\|mo|\\|tu|\\|we|\\|th|\\|fr|\\|sa)*$"
          },
          "totalCalls": {
            "type": "number"
          }
        },
        "required": ["flowId", "name", "dailyCalls", "runCalls", "actions", "dailyRuns", "solution", "on", "containers", "daysOfWeek", "totalCalls"]
      }
    },
    "dailyCalls": {
      "type": "string",
      "pattern": "^[0-9]+$"
    },
    "modified": {
      "type": "string",
      "pattern": "^\\d{2}/\\d{2} - \\d{2}:\\d{2}$"
    }
  },
  "required": ["solutionName", "solutionId", "flows", "dailyCalls", "modified"]
}
```



### Example Export

```
solutionName: AutoReview Analytics
solutionId: c0e4b903-e662-4896-98b3-668abf4574ab
flows:
  - flowId: '0'
    name: AutoReview - Report
    dailyCalls: '365'
    runCalls: '365'
    actions: 6
    dailyRuns: '1'
    solution: AutoReview Analytics
    'on': true
    containers:
      - type: action
        name: Root Actions
        id: '0'
        iterations: 1
        parent: '0'
        actions: 4
        totalCalls: 4
        branch: 'y'
        flow: '0'
        level: 0
      - type: loop
        name: Apply to each article
        typeId: 1
        id: 60f0fead-d1a0-4c6c-83fa-76540ba4e833
        iterations: 180
        parent: '0'
        actions: 2
        totalCalls: 361
        flow: '0'
        branch: 'y'
        level: 1
        dailyCalls: null
    daysOfWeek: su
    totalCalls: 365
  - name: AutoReview - New Flow
    flowId: 969ef200-68ea-49ed-aa06-fcfb6b4ad1fd
    dailyCalls: '14'
    runCalls: '7'
    actions: 8
    dailyRuns: '2'
    solution: AutoReview Analytics
    'on': true
    containers:
      - type: action
        name: Root Actions
        id: 3a064737-af45-486f-acc2-9899e5a1d25a
        iterations: 1
        parent: '0'
        actions: 3
        totalCalls: 3
        flow: 969ef200-68ea-49ed-aa06-fcfb6b4ad1fd
        level: 0
      - type: condition
        name: Condition Is Dev
        typeId: 1
        id: b382d056-0f3b-470e-b1a8-4087726ba828
        iterations: 0.8
        parent: '0'
        actions: 3
        totalCalls: 3.4000000000000004
        flow: 969ef200-68ea-49ed-aa06-fcfb6b4ad1fd
        branch: 'y'
        level: 0
      - type: condition
        name: Condition 1
        typeId: 1
        id: b382d056-0f3b-470e-b1a8-4087726ba828-n
        iterations: 0.2
        parent: '0'
        actions: 2
        totalCalls: 0.4
        flow: 969ef200-68ea-49ed-aa06-fcfb6b4ad1fd
        branch: 'n'
        level: 0
    daysOfWeek: mo|tu|we|th|fr
    totalCalls: 6.800000000000001
dailyCalls: '036514'
modified: 00/04 - 09:37

```

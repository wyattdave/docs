# Input data and output contract

{% hint style="info" %}
Reading this contract is free. Downloading input through the custom-flag manager, testing rules and running custom flags require [Power DevBox Pro](https://power-devbox.lemonsqueezy.com/checkout/buy/729d48f6-cc59-477e-a601-ca99100ffeb3). Standard reviewer data exports remain free.
{% endhint %}

## Download the authoritative input

Load a solution, open **Custom flags**, select a section and choose **Download section JSON**. Each section download is an array of contexts shaped as `{ name, data }`. The rule receives **the context's `data`**, not that outer array. With All sections selected, the download groups context arrays by section key.

The reviewer's **More actions → Download review data (JSON)** also provides section contexts. Do not assume the standalone reviewers' export wrappers still apply in the combined workspace.

| Section key | What `oData` contains | Execution scope |
| --- | --- | --- |
| `app` | An app's AppReview object, including `AppConfig`, `Code`, `Screens`, `Components`, `Variables`, `Connections`, `DataSources`, `Flows` and `Tests` where available. Names are case-sensitive. | Once per app. |
| `auto` | `{ flows: [...] }`, with each flow's `review`, `actionArray`, variable/connection arrays and trigger metadata. | Once over the flow collection. Loop over flows in your code. |
| `copilot` | `{ agents: [...], flows: [...] }`, with agent components and linked-flow summaries. | Once over the agent/flow collections. Loop over agents in your code. |
| `solutions` | Shared solution metadata, environment variables, connection references, dependencies, tables and component inventories; flows include available AutoReview review metadata. | Once for the shared solution. |

Solution-level properties are deliberately excluded from the individual reviewer inputs. An Apps rule must not expect `oData.Solution` or `oData.EnvironmentVariables`. An Automate rule must not expect top-level `environmentVariables`. Put those checks under Solutions and inspect the downloaded lowercase shared schema.

## Rule code

Write the body of a synchronous JavaScript function with `oData` in scope. Use `return`; do not wrap it in `function check(oData) { ... }` unless you call that function and return its result. Guard optional arrays with `|| []` and do not invent a property because a different reviewer's schema has it.

## Array output

The common contract is an array of findings. **Return `[]` when there is no finding.** Each finding needs all five fields:

```javascript
return [{
  area: 'Flow name',
  component: 'Action name',
  type: 'Maintainability',
  level: 'Warning',
  reason: 'Explain the observed issue and what to investigate.',
  how: 'Optional suggested fix',
  category: 'Optional category'
}];
```

Use actual app/flow/agent and component names where possible so scoped reports and component highlighting can associate the finding correctly. Extra fields are retained. Rules may use their existing severity labels; the workspace does not convert every tool to a single risk scale.

## AppReview-compatible output

Legacy Apps rules can return a single pass/fail object:

```javascript
return {
  Name: 'App description',
  Pass: Boolean((oData.AppConfig || {}).AppDescript),
  Level: 'Warning',
  Why: 'A description helps reviewers understand the app.',
  How: 'Add a useful app description.',
  Type: 'app',
  Category: 'maintainability'
};
```

`Pass` must be a Boolean. Only `Pass: false` produces a finding. `Why`, `How`, `Type`, `Level` and `Category` are mapped into the common report and preserved in full details. The combined runner also accepts array findings for Apps; the downloadable original Apps skill intentionally uses its older single-object convention.

## Isolation and limits

Custom JavaScript runs in a fresh, short-lived worker inside an opaque-origin sandbox. It has no DOM, parent window, license state or local-storage access; network/external imports are blocked. Keep rules synchronous and avoid browser APIs or external packages. Workers have a **two-second execution limit** and the runner also has an outer timeout.

A library supports up to **2,000 rules**, each code string up to **100,000 characters**. A rule result is limited to **10,000 findings**. Very large inputs or expensive expressions can still exhaust resources: isolation is not a reason to import untrusted code.

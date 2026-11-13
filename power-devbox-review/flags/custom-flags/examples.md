# Example rules

These examples illustrate the four input scopes. They are deliberately small policy checks, not a complete best-practice pack. Adjust thresholds and recommendations to your team.

{% hint style="info" %}
Reading/downloading the examples is free. Importing, testing and executing these **custom flags** in the app requires [Power DevBox Pro](https://power-devbox.lemonsqueezy.com/checkout/buy/729d48f6-cc59-477e-a601-ca99100ffeb3).
{% endhint %}

[Download the four-rule example JSON](../../.gitbook/assets/review-example-flags.json). Back up your library, import the pack and inspect each section before running it. Each rule name starts with **Guide example** so it is easy to find, disable or remove. The pack has been exercised against synthetic reviewer data; test it against your own exports too.

## Apps: missing description

Runs once per app, retaining AppReview's legacy output format:

```javascript
const oCfg = oData.AppConfig || {};
return {
  Name: 'App description',
  Pass: Boolean(String(oCfg.AppDescript || '').trim()),
  Level: 'Warning',
  Why: 'A description helps reviewers understand the app.',
  How: 'Add a useful description for ' + (oCfg.Name || 'this app') + '.',
  Type: 'app',
  Category: 'maintainability'
};
```

## Automate: actions without notes

Loops through the flow collection and returns one finding for each action with no extracted notes. Requiring notes on every action can be noisy; use it as an example, or narrow it to important connector/action types.

```javascript
const aErrors = [];
for (const oFlow of oData.flows || []) {
  const oReview = oFlow.review || {};
  for (const oAction of oReview.actionArray || []) {
    if (!String(oAction.notes || '').trim()) aErrors.push({
      area: oReview.name || oFlow.displayName,
      component: oAction.name,
      type: 'Maintainability',
      level: 'Warning',
      reason: 'No action note was found in the exported definition.'
    });
  }
}
return aErrors;
```

## Copilot: missing instructions

Skip placeholder agents and check exported instruction text. This detects absence, not instruction quality.

```javascript
return (oData.agents || [])
  .filter(oAgent => !oAgent.isPlaceholder && !String(oAgent.instructions || '').trim())
  .map(oAgent => ({
    area: oAgent.name,
    component: 'Instructions',
    type: 'Quality',
    level: 'Warning',
    reason: 'No agent instructions were found in the export.'
  }));
```

## Solutions: development version policy

This example flags a solution whose numeric major version is zero. Some teams deliberately use zero-major versions, so this is a configurable policy, not a deployment error.

```javascript
if (String(oData.version || '').split('.')[0] !== '0') return [];
return [{
  area: oData.displayName || oData.name || 'Solution',
  component: 'Version',
  type: 'ALM',
  level: 'Warning',
  reason: 'Major version is zero. Confirm this matches the release policy.'
}];
```

## Test expectations

For Apps, try a blank description and a non-empty one. For Automate, try actions with and without notes. For Copilot, try real agents with/without instructions and a placeholder. For Solutions, compare `0.2.0.0` with `2.0.0.0`. Each passing case should produce no finding after normalisation, while failing cases should name the relevant context.

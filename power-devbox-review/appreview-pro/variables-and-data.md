# Variables and data

## Local variables

Open **Local** to inspect context variables, their screen and extracted set/use counts. Look for unclear naming, variables that are set but not used, or logic that depends on screen-local state from an unexpected location.

## Global variables

**Global** lists app-wide variables, with extracted set/use information. Trace where each value is established and where it is consumed. A variable's name should communicate its role and type according to your team's convention.

## Formulas

**Formulas** displays named formulas from the app. Review reusable calculations and dependencies here instead of treating all app logic as event handlers. Check whether calculations duplicated in multiple controls could be expressed more clearly through an appropriate shared formula.

## Collections

**Collections** lists collection names and extracted set/use counts. Check initialization, refresh behaviour and whether a collection is actually required. Counts are static references, not collection row counts, memory measurements or runtime execution counts.

## Data Sources

Open **Data Sources** for the app's data-source names, dataset references and available environment-variable indicators. Check for environment-specific URLs and whether the reference can move safely between environments. A dataset reference does not expose the full live database schema or prove that the current user has access.

## Connections

**Connections** identifies the app's connections/API references. Investigate unnecessary dependencies and whether the intended connector is used. This is not a live audit of credentials, connection ownership, sharing or DLP policy.

## Flows

**Flows** lists flows referenced by the app. Confirm that the references make sense, then open **AutoReview Pro** for the actual flow trigger/action review. A referenced flow might not be included in the same package; an empty or partial list does not prove that all automation dependencies are deployable.

## Interpreting counts safely

{% hint style="info" %}
Inspecting variables and data is free. Turning those checks into executable **custom flags** requires [Power DevBox Pro](https://power-devbox.lemonsqueezy.com/checkout/buy/729d48f6-cc59-477e-a601-ca99100ffeb3).
{% endhint %}

Variable use is inferred from exported source. Comments, text, indirect references and app-format differences can affect text-based checks. Treat a zero-use count as an investigation lead, then confirm in [Parameters or Code Block](build.md). For custom rules, use the exact case-sensitive [input fields](../flags/custom-flags/data-and-output.md), such as `Variables.Global`, not guessed lowercase equivalents.

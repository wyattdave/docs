# Download AI authoring skills

These downloadable skills help an AI coding assistant write custom review flags using documented schemas, output conventions and a feasibility check. They are **authoring instructions**, not importable rule packs and not an automatic review service.

{% hint style="info" %}
**Skill downloads are free.** Creating, testing, importing or running custom flags inside Power DevBox Review requires [Power DevBox Pro](https://power-devbox.lemonsqueezy.com/checkout/buy/729d48f6-cc59-477e-a601-ca99100ffeb3), activated in [Settings](../../settings.md).
{% endhint %}

## Downloads

| Skill | Intended checks | Download |
| --- | --- | --- |
| `powerapps-review-flags` | Canvas-app Power Fx, controls, variables and app data references. | [Power Apps skill ZIP](../../.gitbook/assets/powerapps-review-flags.zip) |
| `powerautomate-review-flags` | Cloud-flow triggers, actions, variables and exception handling. | [Power Automate skill ZIP](../../.gitbook/assets/powerautomate-review-flags.zip) |
| `copilotstudio-review-flags` | Agent topics, tools, knowledge, instructions, skills and MCP permissions. | [Copilot Studio skill ZIP](../../.gitbook/assets/copilotstudio-review-flags.zip) |
| All three | A complete authoring set. | [All custom-flag skills ZIP](../../.gitbook/assets/power-devbox-review-flag-skills.zip) |

Each archive contains a named skill folder with its original **`SKILL.md`**, copied unchanged from the Power DevBox Review source on 13 November 2026. The combined ZIP contains all three folders; no license key, review data or private solution export is included. A fourth Solutions-specific skill is not supplied by the product; use this guide's shared-data contract for solution rules.

## Use with an AI assistant

1. Download and extract a ZIP. Keep the folder name and `SKILL.md` filename intact.
2. If your assistant supports skill directories, put the extracted folder in a skill location supported by that assistant, following its own setup instructions. There is no universal installation directory.
3. Otherwise, open or attach `SKILL.md` and ask the assistant to use it as a reference for the task.
4. Download **current section JSON** from the combined workspace. Inspect/redact it before sharing with any external AI service.
5. Describe one concrete rule, the intended section and an example of passing/failing behaviour.
6. Review the generated JavaScript, then test it in **Custom flags** before saving or sharing it.

Do **not** import a skill ZIP or `SKILL.md` using **Import JSON**. That button accepts rule arrays only.

## Important combined-workspace differences

The original skills describe the standalone reviewers and intentionally remain unchanged in these downloads. Apply these adjustments when using them here:

* Inputs downloaded from the combined workspace are **context arrays**. The rule receives the context's `data`, not the outer array; Apps runs once per app.
* Automate receives `{ flows }`; Copilot receives `{ agents, flows }`. Their top-level solution metadata and shared inventories are excluded.
* Checks for solution metadata, missing dependencies, shared environment variables, connection references or tables belong under **Solutions**. Use a current Solutions sample, not the legacy standalone schema.
* In an exported/imported workspace pack, include `section`: `app`, `auto`, `copilot` or `solutions`. Alternatively, select the matching section when importing a legacy pack.
* The legacy Apps skill returns a single `Pass` object. The combined workspace supports it and also accepts the common finding-array contract.
* Treat regex/text checks as heuristics. Do not ask the assistant to fabricate runtime analytics, permissions, DLP policy or fields absent from the downloaded data.

The authoritative combined-workspace contract is [Input data and output contract](data-and-output.md).

## Example request

> Use the powerautomate-review-flags skill as a reference. Target Power DevBox Review's **auto** section, whose oData contains only flows. Write a synchronous flag for HTTP actions with no exported notes. Use actual flow/action names, guard optional arrays and return finding objects. Do not infer runtime security or solution-level configuration. Produce a JSON rule entry with section auto, and explain possible false positives. I will test it against the current section data before importing.

For a Solutions rule, replace the product-specific scope with **solutions** and provide a redacted current Solutions context. Ask the assistant to map every required fact to an actual field before writing code.

## Keep generated rules safe

Read the code, test both outcomes and export a library backup before importing changes. Skills improve consistency; they do not make generated code trusted or findings correct. The app's sandbox blocks network access for a rule, but **sharing a JSON sample with your assistant is a separate disclosure decision**.

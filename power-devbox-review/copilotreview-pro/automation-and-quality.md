# Automation, evaluations and flags

## Agent Flows

**Agent Flows** shows the flows associated with the selected agent, including the available linkage/status and summary information. Review trigger inputs, outputs, response behaviour, connection references and whether a required flow is included in the solution.

CopilotReview's flow data is a **summary**, not the full action-level schema. Switch to **AutoReview Pro** to inspect individual actions, retries, variables and exception handling. A referenced flow outside the package may require separate evidence.

## Connections

**Connections** brings together the selected agent's connection-reference and environment-variable usage. Check logical names, used-by information and available definition details. Compare this with the complete shared inventory under **Solution** when investigating an unused declaration or deployment dependency.

Package configuration may include defaults or values. Treat downloaded JSON and raw files as potentially sensitive. Do not assume that one export reveals the values or permissions in every target environment.

## AI Prompts

**AI Prompts** lists prompt/model components associated with the agent. Open a component to inspect available prompt text, model configuration, inputs and output formats. Check environment-specific assumptions, model policy and the expected input/output contract.

A model name in the definition is not evidence of measured quality, cost, credit usage or latency. Review any generated-code/configuration content according to your normal source-review process.

## Evaluations

**Evaluations** shows the exported evaluation/test-set and case definitions. Review what scenarios are covered and what is missing, particularly unsafe requests, tool failures and hand-off paths.

The reviewer does **not run these evaluations** or fetch their results. A test case appearing in the table does not mean it passed. Keep execution results from your actual test process alongside the static review.

## Flags

**Flags**, or the header **Custom flag report**, opens custom findings for the selected agent. **All flags** opens the central cross-section report. Use **Manage flags** to edit the Copilot library, then rerun the checks.

Broken references and publish diagnostics are also useful exported evidence on the agent overview/detail. They are not a substitute for a live publish/deployment check. Review [execution errors](../flags/flag-report.md#execution-errors) before relying on a low custom-finding count.

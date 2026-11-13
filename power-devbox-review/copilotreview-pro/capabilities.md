# Tools, knowledge and variables

## Tools

Open **Tools** for the agent's callable capabilities. Review names, model descriptions, action kind, linked flow/connector, inputs and outputs, connection mode and confirmation settings where exported.

Descriptions should tell the orchestrator when a tool is appropriate and what it does. Inspect environment-specific IDs and expressions in inputs. For consequential actions, verify that the intended confirmation and end-user/author connection behaviour is represented in the definition.

### MCP permissions

{% hint style="info" %}
Inspecting tool definitions is free. Executing the MCP **custom-flag rules** and viewing their findings requires [Power DevBox Pro](https://power-devbox.lemonsqueezy.com/checkout/buy/729d48f6-cc59-477e-a601-ca99100ffeb3).
{% endhint %}

For MCP tools, available review data includes whether all tools are allowed and any explicit allowed-tool list. The default Copilot custom rules warn when a connector allows **all tools** or explicitly allows **more than five** tools. These are review thresholds, not a proof that the connector is unsafe or a universal limit imposed by Microsoft.

Use the actual business requirement and least-privilege policy to decide whether a finding should lead to a configuration change. Default custom-rule execution requires Pro.

## Knowledge

**Knowledge** lists source definitions and packaged knowledge files. Inspect source type/site, descriptions, activation and available conditions. Open a row for definition details.

The source reference does not retrieve the contents of a SharePoint site or other external knowledge store. It does not prove indexing is complete, that the agent sees current content, or that target users have appropriate permissions. Uploaded knowledge-file inventory is likewise not an assessment of factual accuracy.

## Variables and entities

**Variables** shows exported agent/global variable information such as scope, data type, description and extracted set/use references. Available entity information is shown with the agent's relevant configuration/details.

Check naming and intended exposure, investigate unused state, and follow topic references for context. Do not infer runtime values, user isolation or a complete data-leak assessment from static counts alone.

## Useful cross-checks

* Follow tool-to-flow links and inspect the flow in AutoReview.
* Compare connection-reference declarations with actual component usage.
* Check instructions against the tools and knowledge the agent really has.
* Use the package [file browser](../solution/solution-files.md) if an extracted field needs confirmation.

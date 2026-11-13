# Audit checks and limitations

The audit reads Dataverse organization/OrgDB settings, role associations, solution-aware connector records, and Power Platform management/governance settings. Availability depends on the environment version, database, endpoint, and caller permissions.

## Coverage by section

| Section | Included checks |
| --- | --- |
| Roles | System Administrator, System Customizer, Environment Maker, Bot Transcript Viewer; direct user/application-user/team assignments across business-unit role copies |
| AI features | Owner/editor transcript access, transcript recording, embedded maker credentials, Work IQ Business Applications, Dataverse MCP GA/preview, preview/experimental AI models, Anthropic external-model settings |
| Power Automate Desktop | Copilot Studio computer use, computer-use Purview logs, hosted machine groups, hosted machines, default VM image sharing |
| Dataverse | Default solution creation for canvas apps/flows and cloud-flow history retention |
| Security | Block unmanaged customizations; Attachment table security; attachment file/MIME/size restrictions; canvas PCF; code apps; generative pages; cross-business-unit ownership; IP cookie binding; firewall/audit/allow-list settings; inactivity settings; code-app, canvas, and model-driven CSP |
| Auditing | Audit enabled and retention |
| Custom connectors | Solution-aware Dataverse custom connector logical/display names and managed state |

Existing saved configurations preserve their selections. If upgrading from a version before **Enable security on the Attachment table**, explicitly select that check or toggle the Security section on to include it. It is separate from attachment file restrictions.

## Read results accurately

* **Read** means a value was returned, not that it meets a security baseline.
* **Unavailable** means no explicit readable value, no required database/adapter, or no matching role, as appropriate. It does **not** mean Disabled.
* **Error** retains authentication, permissions, throttling, or request failures. A failed inventory page is not turned into a successful empty result.
* **Not returned** identifies missing subfields in compound settings. False, zero, and explicitly empty values are preserved rather than hidden.

OrgDB checks prefer explicit values, then try the read-only named-setting action when needed. The existence of a portal rollout flag is not substituted for the environment setting. Negative blocking flags for AI features are inverted to describe whether the requested capability is allowed.

## Important boundaries

* Role inventories do not expand Entra group/team membership, inherited users, or implicit tenant administrator access. They include direct assignments visible to the caller, including disabled users.
* Matching connector inventories compare logical names and managed state, not implementation or credentials. Non-solution connectors are outside this Dataverse inventory.
* Anthropic's environment value, Microsoft 365 availability, and admin-control lock state are separate. A locked control is not assumed to mean the model is disabled.
* Dataverse MCP does not inventory per-client allow lists. Work IQ is not replaced with an unrelated search/indexing flag.
* The computer-use check is explicitly for **Copilot Studio**, not a claimed separate PAD policy.
* Cloud-flow history retention of zero disables ingestion. Audit retention of -1 displays **Forever**.
* Effective environment-group inheritance is outside this audit. Null/unset settings are not silently replaced by portal defaults.
* Supported organization URLs are HTTPS `*.dynamics.com` commercial-cloud endpoints. Sovereign clouds need additional support.

The management/governance contracts can change independently of Dataverse. Use an appropriately privileged account and compare critical findings with Microsoft administration tools. The audit is an aid to review, not a compliance certification.

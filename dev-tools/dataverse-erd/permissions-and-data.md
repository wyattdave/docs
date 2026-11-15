# Permissions and data handling

Understand the extension's browser access and the information involved before using it in your organization.

## Browser permissions

The public version 1.0.0 manifest requests:

| Permission | Purpose in the implementation |
| --- | --- |
| `webRequest` | Observe authorization headers on supported Dataverse API requests. |
| `storage` | Keep captured tokens and environment/tab associations in extension-local storage. |
| `alarms` | Periodically check for expired tokens and update token status. |
| `tabs` | Identify the active maker-portal tab, track its environment/solution, and open the viewer. |

Site access is declared for these HTTPS hosts and paths:

* `*.dynamics.com/*`
* `make.powerautomate.com/environments/*`
* `make.powerapps.com/environments/*`
* `make.preview.powerapps.com/environments/*`
* `copilotstudio.preview.microsoft.com/environments/*`

These are the declared hosts, not a promise of support for every Microsoft cloud or portal hostname. In particular, the current viewer validates a Dataverse organization URL ending in `.dynamics.com`; do not assume a different sovereign-cloud suffix works.

## Session and storage

The extension observes the authorization token already being sent to the Dataverse Web API. It stores tokens by organization URL, token expiry, tab-to-environment/solution associations and environment mappings in `chrome.storage.local`. It can retain information for more than one environment.

The token-check alarm runs every five minutes, and setup also prunes expired tokens. The extension does not sign in independently or silently refresh authentication for you; refresh or reauthenticate in the maker portal when the session needs renewal.

{% hint style="danger" %}
**Treat captured bearer tokens as credentials.** Never paste extension storage, Authorization headers or complete network traces into documentation or a public issue. Signing out of a portal is not a guarantee that this extension's locally stored state was immediately cleared. The current interface has no dedicated clear-token control.
{% endhint %}

## What is read and generated?

The viewer reads solution components, table and column metadata, lookup relationships and choice details. Role export additionally reads roles, privileges and table metadata. The implementation's metadata requests are read-only; creating a diagram does not modify tables, solution membership, roles or business records.

Diagram rendering, Markdown generation, image exports and Excel workbooks are produced in the browser using bundled Mermaid and ExcelJS libraries. The public extension source defines no separate backend upload service for these operations. Requests to your Dataverse environment are still required; this is not an offline metadata viewer.

That description is based on the public source, not a certification of browser, Microsoft-service or organization-wide data handling. Your organization's extension and data policies still apply.

## Before sharing output

Although the tool documents metadata rather than business-record contents, metadata can still be sensitive. Review:

* Environment hostnames, solution names and versions.
* Internal table/column names and descriptions.
* Security-role names and permission scopes.
* Lookup targets and choice values that reveal internal processes.

Store exports only in approved locations. Redact screenshots and error messages before sharing them. Removing the extension is managed through `chrome://extensions` or `edge://extensions`; contact your administrator if browser policy controls installation or site access.

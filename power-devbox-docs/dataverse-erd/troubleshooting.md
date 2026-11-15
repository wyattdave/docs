# Troubleshooting

Start with the popup's token status, then check the environment, selected solution and viewer progress. Do not paste a token into the extension or grant broad administrator privileges as a first troubleshooting step.

## No Dataverse token or a red exclamation badge

**What it means:** the extension has not captured a usable token, or its captured token has expired. The badge indicates that no stored environment currently has a valid token; it is not a detailed environment-specific access check.

1. Open the target environment in Power Apps or Power Automate and sign in.
2. Open **Solutions** and the solution you want to diagram.
3. Refresh the portal so it makes a Dataverse request after the extension is installed.
4. Reopen the extension while that tab is active.
5. Check browser extension settings allow access to the supported sites. On a managed device, ask your administrator if policy blocks that access.

If your environment uses a host outside the [declared supported hosts](permissions-and-data.md#browser-permissions), it may not be compatible with this version.

## Wrong environment token

**What it means:** the active portal's environment could not be matched to a captured token, even though a token for another organization may exist.

Open or refresh a solution in the intended environment, then reopen the popup. Check the displayed organization host before continuing. If several environment tabs are open, keep the intended tab active; do not assume the most recently used organization is the correct one.

## Could not load solutions

The popup lists visible solutions returned by Dataverse, ordered by friendly name. It does not search every environment in your tenant.

* Confirm the organization shown in the popup.
* Refresh your signed-in session and reopen the extension.
* Check you can open the expected solution in the maker portal with the same account.
* For a 401 response, renew the sign-in session. For a 403 response, ask an administrator to check the relevant read permissions.

If the list says **No solutions found**, confirm the target environment has visible solutions available to your account.

## Create Diagram is disabled

The button requires both a valid captured token and a selected solution. Resolve token or solution-loading errors, then choose an entry in **Solution**. Loading the popup alone is not enough.

## This solution contains no Dataverse tables

The solution has no diagrammable table components, or table metadata could not be resolved. A solution containing only apps, flows or roles does not produce a table ERD. Intersect tables are excluded.

Confirm the solution includes the tables you expect and that your account can read their metadata. Some table-resolution failures are logged and skipped, so an unexpectedly small table count also needs investigation.

## A table, column or relationship is missing

First compare the result with the documented scope:

* Only custom lookup-based relationships are retained; many-to-many and most standard relationships are not shown.
* Column lists focus on custom columns and selected standard columns.
* External tables can appear in the ERD but are excluded from the table-design export.
* Some optional lookup and choice detail requests can fail without stopping the whole report.

See [Diagram and Mermaid](diagram.md) and [Exports](exports.md) before treating an omission as a defect. If it should be in scope, confirm the metadata is readable in Dataverse and create a fresh diagram after any changes.

## Diagram is visible, but Excel or Markdown is unavailable

The diagram is rendered before the additional column details load. Wait for that progress stage to finish. If an error appears, the diagram may still be usable while the later table-design export is not complete.

Refresh the portal session, reopen the extension and generate again. Do not assume a visible diagram proves every later metadata request succeeded.

## Role Excel is missing or fails

The button appears only when solution roles were discovered successfully. Check the role is included in this solution and that your account can read it. During export, the account also needs access to privilege and table metadata.

An empty or unexpected worksheet is not evidence of effective user access. Read the [role-export scope and limitations](security-roles.md) and validate important results in the Dataverse role editor.

## PNG export fails

Large diagrams can exceed browser canvas or memory limits. Use **Save SVG** instead. Reducing viewer zoom does not reduce the base-size PNG export.

## Copy failed

Keep the viewer tab active and retry the copy action. For Mermaid, expand **Mermaid source** and copy its text manually. For field documentation, download Excel as an alternative.

## Extension error or background worker unavailable

Open `chrome://extensions` or `edge://extensions` and confirm the extension is enabled. For an unpacked development installation, select **Reload** after source changes. Then refresh the maker-portal page and reopen the popup to capture the current session again.

## Report a problem safely

Use the [GitHub repository's issue tracker](https://github.com/wyattdave/Power-DevBox-Datverse-ERD/issues) and include:

* Browser and extension version, and whether installed from Chrome, Edge or unpacked source.
* The failing stage: token capture, solution loading, diagram rendering, table design or role export.
* Minimal reproduction steps and the sanitized error/status code.
* Whether the issue occurs with a small non-sensitive test solution.
* A redacted screenshot if it helps explain the issue.

Do not include bearer tokens, storage dumps, customer data, tenant/environment identifiers or confidential schema details. Share only the minimum evidence needed to reproduce the problem.

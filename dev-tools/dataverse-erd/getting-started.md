# Getting started

Create your first Dataverse diagram from a solution in the maker portal.

## Before you begin

You need:

* Google Chrome or Microsoft Edge on a device where you can install extensions.
* A signed-in account with access to a Dataverse environment.
* A solution containing Dataverse tables, and permission to read its solution, table, column and relationship metadata.
* Additional access to security-role and privilege metadata if you want a [role-permissions export](security-roles.md).

A solution containing only apps or flows has no tables to diagram. The extension does not require a solution ZIP, Node.js, an API key or a separate application installation.

## 1. Install the extension

1. Open the listing for your browser:
   * [Chrome Web Store](https://chromewebstore.google.com/detail/power-devbox-dataverse-er/mffdldfcdccomfdofoohglofiemgbpkh).
   * [Microsoft Edge Add-ons](https://microsoftedge.microsoft.com/addons/detail/power-devbox-dataverse-er/jgfjhddjjidpnmmpbnahdjmelfooendd).
2. Select **Add to Chrome** or **Get**, then review and confirm the requested permissions.
3. Open your browser's Extensions menu and pin **Power DevBox Dataverse ERD** if you want quick toolbar access.

See [Permissions and data handling](permissions-and-data.md) for why it needs access to supported sites.

## 2. Open the target environment

1. Open [Power Apps](https://make.powerapps.com/) or [Power Automate](https://make.powerautomate.com/) and sign in.
2. Choose the environment you want to document.
3. Open **Solutions**, then open the target solution so the portal makes Dataverse requests.
4. If the extension was installed after the portal loaded, refresh the portal page before continuing.

The extension detects an authorization token from requests to the Dataverse Web API. Simply opening a browser tab without loading Dataverse content may not be enough.

## 3. Select the solution

1. Keep the target maker-portal tab active and open **Power DevBox Dataverse ERD**.
2. Look for **Dataverse token captured**. The popup shows the Dataverse organization host and approximate token expiry.
3. Check the organization is the environment you intended to use.
4. In **Solution**, select the solution. Entries show the friendly name and version; the open solution may already be selected automatically.
5. Select **Create Diagram**. A viewer opens in a new browser tab.

{% hint style="warning" %}
**Check the environment before generating.** If you switch environments, open or refresh the solution in the new environment and reopen the popup. A token captured for another environment is not sufficient. Never share a screenshot of your organization host without checking whether it is safe to disclose.
{% endhint %}

## 4. Wait for the viewer to finish

The viewer loads the solution, resolves its tables and relationships, renders the ERD, then loads additional column details and checks for security roles. Larger solutions take more requests and may take longer.

Expected results:

* The header shows the solution name, version, solution-table count and relationship count, plus an external-dependency count when relevant.
* The diagram is visible and **Copy Mermaid**, **Save SVG** and **Save PNG** become available after rendering.
* **Copy Markdown** and **Download Excel** become available after the table-design details load.
* **Role Excel** or **Roles Excel (n)** appears only when solution roles have been found.

Buttons becoming available at different times is normal. If the diagram is visible but a later stage fails, check the error before treating the table-design or role output as complete.

Continue with [Diagram and Mermaid](diagram.md) or [Exports](exports.md). For a missing token, disabled button or request failure, see [Troubleshooting](troubleshooting.md).

## Optional: load the public source locally

For development or source inspection, [clone or download the repository](https://github.com/wyattdave/Power-DevBox-Datverse-ERD), extract it if needed, and open `chrome://extensions` or `edge://extensions`. Enable **Developer mode**, select **Load unpacked**, and choose the folder containing `manifest.json`.

There is no build or package-install step; Mermaid and ExcelJS are bundled. After changing source files, reload the extension from the browser's extensions page and reopen the popup. Ordinary users should use the store installation above.

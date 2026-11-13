# Privacy and permissions

The extension runs PDAC locally in the browser and calls Microsoft services as the selected account. Local execution does not make administrative data public-safe or remove the need for tenant approval.

## Requested browser permissions

| Permission | Why it is used |
| --- | --- |
| `storage` | Local settings, account, and authentication persistence |
| `alarms` | Daily report checks and weekly tracking checks |
| `tabs` | Microsoft sign-in redirect handling and app/browser flows |

Host access covers `login.microsoftonline.com`, `*.dynamics.com`, `api.powerapps.com`, `api.bap.microsoft.com`, `api.powerplatform.com`, and `*.environment.api.powerplatform.com`. These support authentication and the Power Platform/Dataverse APIs, including environment-scoped audit governance reads.

The manifest does not request access to every website, cookie access, page-injection content scripts, or the Downloads API permission. Report files use normal browser downloads. Runtime libraries are packaged with the extension, not loaded as executable code from a CDN.

## What is stored locally?

* Settings, schedule/account information, and Microsoft Entra refresh tokens use extension-local storage.
* Cached report files, report totals, record inventories, and dedicated weekly data use IndexedDB as applicable.
* UI preferences, such as table-column visibility, can use local browser storage.
* Audit preferences save locally per account; audit **results** remain in page memory until refresh/context clearing.

Normal websites cannot read `chrome.storage.local`. However, someone controlling the signed-in operating-system/browser profile can access or remove its local data. Refresh tokens are credentials: protect the OS account and profile, use your organization's device controls, and never share storage dumps.

## No automatic cross-device synchronization

Signing into the same Microsoft identity on another installation does not synchronize PDAC's local credentials, schedules, files, or history. [Trend workbooks](settings/trend-data.md) transfer supported totals only; they are not a full installation backup.

## Exports and transcripts

Solution ZIPs, deployment settings, environment audits, weekly HTML, role files, and activity workbooks may contain confidential configuration, identities, URLs, or business metadata. Review recipients and storage locations before sharing.

Session details redact obvious sensitive content before rendering, but that is not guaranteed anonymization. Inspect transcript content and screenshots yourself. Do not attach access tokens, refresh tokens, authentication headers, cookies, or unredacted traces to public issues.

## Administrative authority

PDAC does not elevate your Microsoft privileges. Tenant policies, licensing, environment membership, Dataverse roles, and API authorization still apply. Use the least privilege appropriate to the task, and distinguish the read-only audit/reporting workflows from buttons that perform real writes.

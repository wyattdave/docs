# Documentation workspace path changes

Canonical root for the replacement app: **https://docs.powerdevbox.com**. The current preview at `https://devbox-docs.powerdevbox.workers.dev` uses the same paths. This does not change DNS or configure redirects.

The previous attempt only moved files within `power-devbox-docs` and changed sidebar headings. This correction registers seven real spaces in `gitbook-docs.yaml` and moves the tool pages out of `power-devbox-docs`. Existing AppReview Pro, AutoReview Pro, PDAC and Power DevBox Review spaces are unchanged. Power DevBox Docs retains its home and shared getting-started pages.

## Workspace destinations

* AutoReview: https://docs.powerdevbox.com/autoreview/
* AppReview: https://docs.powerdevbox.com/appreview/
* Flow Utilizer: https://docs.powerdevbox.com/flow-utilizer/
* Solution Explorer: https://docs.powerdevbox.com/solution-explorer/
* Unmanaged: https://docs.powerdevbox.com/unmanaged/
* Power DevBox Utility: https://docs.powerdevbox.com/power-devbox-utility/
* Dev Tools: https://docs.powerdevbox.com/dev-tools/

Dev Tools contains **Chrome Extensions** (Share, Shortcut, Exception, Dataverse ERD) and **VS Code Extensions** (Power Automate Utility). Power DevBox Utility is a separate workspace.

## All moved pages: original app paths to final URLs

Old paths are relative to the app origin. New URLs use the requested future canonical root. Folder README pages use trailing slashes; other pages have no `.md` extension. Keep any `#heading` fragment when updating links.

| Old path (before either attempt) | New URL |
| --- | --- |
| `/power-devbox-docs/appreview/appreview-chromium-extension/` | https://docs.powerdevbox.com/appreview/ |
| `/power-devbox-docs/appreview/appreview-chromium-extension/app-settings` | https://docs.powerdevbox.com/appreview/app-settings |
| `/power-devbox-docs/appreview/appreview-chromium-extension/code-block` | https://docs.powerdevbox.com/appreview/code-block |
| `/power-devbox-docs/appreview/appreview-chromium-extension/components` | https://docs.powerdevbox.com/appreview/components |
| `/power-devbox-docs/appreview/appreview-chromium-extension/connections` | https://docs.powerdevbox.com/appreview/connections |
| `/power-devbox-docs/appreview/appreview-chromium-extension/data-source` | https://docs.powerdevbox.com/appreview/data-source |
| `/power-devbox-docs/appreview/appreview-chromium-extension/diagram` | https://docs.powerdevbox.com/appreview/diagram |
| `/power-devbox-docs/appreview/appreview-chromium-extension/flags` | https://docs.powerdevbox.com/appreview/flags |
| `/power-devbox-docs/appreview/appreview-chromium-extension/known-bugs-limitations` | https://docs.powerdevbox.com/appreview/known-bugs-limitations |
| `/power-devbox-docs/appreview/appreview-chromium-extension/report-sections` | https://docs.powerdevbox.com/appreview/report-sections |
| `/power-devbox-docs/appreview/appreview-chromium-extension/solution` | https://docs.powerdevbox.com/appreview/solution |
| `/power-devbox-docs/appreview/appreview-chromium-extension/variables` | https://docs.powerdevbox.com/appreview/variables |
| `/power-devbox-docs/autoreview/api/` | https://docs.powerdevbox.com/autoreview/api/ |
| `/power-devbox-docs/autoreview/api/v1/` | https://docs.powerdevbox.com/autoreview/api/v1/ |
| `/power-devbox-docs/autoreview/api/v1/data-api-v1` | https://docs.powerdevbox.com/autoreview/api/v1/data-api-v1 |
| `/power-devbox-docs/autoreview/api/v1/files-api-v1` | https://docs.powerdevbox.com/autoreview/api/v1/files-api-v1 |
| `/power-devbox-docs/autoreview/api/v1/information-api-v1` | https://docs.powerdevbox.com/autoreview/api/v1/information-api-v1 |
| `/power-devbox-docs/autoreview/api/v2/` | https://docs.powerdevbox.com/autoreview/api/v2/ |
| `/power-devbox-docs/autoreview/api/v2/data-api-v2` | https://docs.powerdevbox.com/autoreview/api/v2/data-api-v2 |
| `/power-devbox-docs/autoreview/api/v2/diagram-api-v2` | https://docs.powerdevbox.com/autoreview/api/v2/diagram-api-v2 |
| `/power-devbox-docs/autoreview/api/v2/files-api-v2` | https://docs.powerdevbox.com/autoreview/api/v2/files-api-v2 |
| `/power-devbox-docs/autoreview/api/v2/information-api-v2` | https://docs.powerdevbox.com/autoreview/api/v2/information-api-v2 |
| `/power-devbox-docs/autoreview/autoreview-app` | https://docs.powerdevbox.com/autoreview/autoreview-app |
| `/power-devbox-docs/autoreview/autoreview-chromium-extension` | https://docs.powerdevbox.com/autoreview/autoreview-chromium-extension |
| `/power-devbox-docs/autoreview/autoreview-power-platform-connector/` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/ |
| `/power-devbox-docs/autoreview/autoreview-power-platform-connector/diagam-v2` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/diagam-v2 |
| `/power-devbox-docs/autoreview/autoreview-power-platform-connector/file-v1` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/file-v1 |
| `/power-devbox-docs/autoreview/autoreview-power-platform-connector/file-v2` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/file-v2 |
| `/power-devbox-docs/autoreview/autoreview-power-platform-connector/http` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/http |
| `/power-devbox-docs/autoreview/autoreview-power-platform-connector/info-v1-and-v2` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/info-v1-and-v2 |
| `/power-devbox-docs/autoreview/autoreview-power-platform-connector/json-v1-and-v2` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/json-v1-and-v2 |
| `/power-devbox-docs/autoreview/autoreview-power-platform-connector/using-connector` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/using-connector |
| `/power-devbox-docs/autoreview/autoreview-vs-code-extension` | https://docs.powerdevbox.com/autoreview/autoreview-vs-code-extension |
| `/power-devbox-docs/autoreview/configs/` | https://docs.powerdevbox.com/autoreview/configs/ |
| `/power-devbox-docs/autoreview/configs/complexity/` | https://docs.powerdevbox.com/autoreview/configs/complexity/ |
| `/power-devbox-docs/autoreview/configs/complexity/complexity-default-values` | https://docs.powerdevbox.com/autoreview/configs/complexity/complexity-default-values |
| `/power-devbox-docs/autoreview/configs/complexity/complexity-template` | https://docs.powerdevbox.com/autoreview/configs/complexity/complexity-template |
| `/power-devbox-docs/autoreview/configs/naming-convention/` | https://docs.powerdevbox.com/autoreview/configs/naming-convention/ |
| `/power-devbox-docs/autoreview/configs/naming-convention/naming-convention-default-value` | https://docs.powerdevbox.com/autoreview/configs/naming-convention/naming-convention-default-value |
| `/power-devbox-docs/autoreview/configs/naming-convention/naming-template` | https://docs.powerdevbox.com/autoreview/configs/naming-convention/naming-template |
| `/power-devbox-docs/autoreview/configs/ratings/` | https://docs.powerdevbox.com/autoreview/configs/ratings/ |
| `/power-devbox-docs/autoreview/configs/ratings/ratings-default-value` | https://docs.powerdevbox.com/autoreview/configs/ratings/ratings-default-value |
| `/power-devbox-docs/autoreview/configs/ratings/ratings-template` | https://docs.powerdevbox.com/autoreview/configs/ratings/ratings-template |
| `/power-devbox-docs/autoreview/configs/scoring/` | https://docs.powerdevbox.com/autoreview/configs/scoring/ |
| `/power-devbox-docs/autoreview/configs/scoring/scoring-default-values` | https://docs.powerdevbox.com/autoreview/configs/scoring/scoring-default-values |
| `/power-devbox-docs/autoreview/configs/scoring/scoring-template` | https://docs.powerdevbox.com/autoreview/configs/scoring/scoring-template |
| `/power-devbox-docs/autoreview/data-json` | https://docs.powerdevbox.com/autoreview/data-json |
| `/power-devbox-docs/autoreview/files/` | https://docs.powerdevbox.com/autoreview/files/ |
| `/power-devbox-docs/autoreview/files/compare-with-previous` | https://docs.powerdevbox.com/autoreview/files/compare-with-previous |
| `/power-devbox-docs/autoreview/files/csv-files` | https://docs.powerdevbox.com/autoreview/files/csv-files |
| `/power-devbox-docs/autoreview/files/diagram` | https://docs.powerdevbox.com/autoreview/files/diagram |
| `/power-devbox-docs/autoreview/files/exceptions` | https://docs.powerdevbox.com/autoreview/files/exceptions |
| `/power-devbox-docs/autoreview/files/report` | https://docs.powerdevbox.com/autoreview/files/report |
| `/power-devbox-docs/autoreview/files/review` | https://docs.powerdevbox.com/autoreview/files/review |
| `/power-devbox-docs/autoreview/files/solution` | https://docs.powerdevbox.com/autoreview/files/solution |
| `/power-devbox-docs/autoreview/menu` | https://docs.powerdevbox.com/autoreview/menu |
| `/power-devbox-docs/dev-tools/dataverse-erd/` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/ |
| `/power-devbox-docs/dev-tools/dataverse-erd/diagram` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/diagram |
| `/power-devbox-docs/dev-tools/dataverse-erd/exports` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/exports |
| `/power-devbox-docs/dev-tools/dataverse-erd/getting-started` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/getting-started |
| `/power-devbox-docs/dev-tools/dataverse-erd/permissions-and-data` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/permissions-and-data |
| `/power-devbox-docs/dev-tools/dataverse-erd/security-roles` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/security-roles |
| `/power-devbox-docs/dev-tools/dataverse-erd/troubleshooting` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/troubleshooting |
| `/power-devbox-docs/flow-utilizer/account/` | https://docs.powerdevbox.com/flow-utilizer/account/ |
| `/power-devbox-docs/flow-utilizer/account/account-download` | https://docs.powerdevbox.com/flow-utilizer/account/account-download |
| `/power-devbox-docs/flow-utilizer/charts` | https://docs.powerdevbox.com/flow-utilizer/charts |
| `/power-devbox-docs/flow-utilizer/flow-screen/` | https://docs.powerdevbox.com/flow-utilizer/flow-screen/ |
| `/power-devbox-docs/flow-utilizer/flow-screen/flow-tags` | https://docs.powerdevbox.com/flow-utilizer/flow-screen/flow-tags |
| `/power-devbox-docs/flow-utilizer/flow-screen/solution-download` | https://docs.powerdevbox.com/flow-utilizer/flow-screen/solution-download |
| `/power-devbox-docs/flow-utilizer/flow-utilizer-start` | https://docs.powerdevbox.com/flow-utilizer/ |
| `/power-devbox-docs/flow-utilizer/install` | https://docs.powerdevbox.com/flow-utilizer/install |
| `/power-devbox-docs/flow-utilizer/solution-screen` | https://docs.powerdevbox.com/flow-utilizer/solution-screen |
| `/power-devbox-docs/dev-tools/power-automate-utility-vs-code` | https://docs.powerdevbox.com/dev-tools/power-automate-utility-vs-code |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/` | https://docs.powerdevbox.com/dev-tools/chrome-extensions |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/exception` | https://docs.powerdevbox.com/dev-tools/exception |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/share/` | https://docs.powerdevbox.com/dev-tools/share/ |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/share/share-demo-videos` | https://docs.powerdevbox.com/dev-tools/share/share-demo-videos |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/shortcut` | https://docs.powerdevbox.com/dev-tools/shortcut |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/` | https://docs.powerdevbox.com/power-devbox-utility/ |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/classic-ui-clipboard` | https://docs.powerdevbox.com/power-devbox-utility/classic-ui-clipboard |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/new-ui-clipboard` | https://docs.powerdevbox.com/power-devbox-utility/new-ui-clipboard |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/utility-demo-videos` | https://docs.powerdevbox.com/power-devbox-utility/utility-demo-videos |
| `/power-devbox-docs/v2-v3.2.0-update` | https://docs.powerdevbox.com/autoreview/v2-v3.2.0-update |
| `/power-devbox-docs/web-apps/solution-explorer` | https://docs.powerdevbox.com/solution-explorer/ |
| `/power-devbox-docs/web-apps/unmanaged` | https://docs.powerdevbox.com/unmanaged/ |

## Intermediate paths created by the previous attempt

Also replace these if a site already adopted the previous map. Other intermediate paths equal the old paths above.

| Intermediate old path | Final URL |
| --- | --- |
| `/power-devbox-docs/dataverse-erd/` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/ |
| `/power-devbox-docs/dataverse-erd/diagram` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/diagram |
| `/power-devbox-docs/dataverse-erd/exports` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/exports |
| `/power-devbox-docs/dataverse-erd/getting-started` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/getting-started |
| `/power-devbox-docs/dataverse-erd/permissions-and-data` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/permissions-and-data |
| `/power-devbox-docs/dataverse-erd/security-roles` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/security-roles |
| `/power-devbox-docs/dataverse-erd/troubleshooting` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/troubleshooting |
| `/power-devbox-docs/power-automate-utility-vs-code` | https://docs.powerdevbox.com/dev-tools/power-automate-utility-vs-code |
| `/power-devbox-docs/power-devbox-chromium-extensions/` | https://docs.powerdevbox.com/dev-tools/chrome-extensions |
| `/power-devbox-docs/power-devbox-chromium-extensions/exception` | https://docs.powerdevbox.com/dev-tools/exception |
| `/power-devbox-docs/power-devbox-chromium-extensions/share/` | https://docs.powerdevbox.com/dev-tools/share/ |
| `/power-devbox-docs/power-devbox-chromium-extensions/share/share-demo-videos` | https://docs.powerdevbox.com/dev-tools/share/share-demo-videos |
| `/power-devbox-docs/power-devbox-chromium-extensions/shortcut` | https://docs.powerdevbox.com/dev-tools/shortcut |
| `/power-devbox-docs/power-devbox-chromium-extensions/utility/` | https://docs.powerdevbox.com/power-devbox-utility/ |
| `/power-devbox-docs/power-devbox-chromium-extensions/utility/classic-ui-clipboard` | https://docs.powerdevbox.com/power-devbox-utility/classic-ui-clipboard |
| `/power-devbox-docs/power-devbox-chromium-extensions/utility/new-ui-clipboard` | https://docs.powerdevbox.com/power-devbox-utility/new-ui-clipboard |
| `/power-devbox-docs/power-devbox-chromium-extensions/utility/utility-demo-videos` | https://docs.powerdevbox.com/power-devbox-utility/utility-demo-videos |

## Original GitBook links on the existing custom domain

These are legacy GitBook browser paths, not replacement-app routes. The old default GitBook space had no `/power-devbox-docs` prefix and used SUMMARY nesting for paths. The table maps those original paths directly to final app URLs, for updating main-site links during the switch. For GitBook Markdown export URLs, remove the final `.md` before matching; the replacement app uses clean routes.

| Original GitBook path | Final app URL |
| --- | --- |
| `/autoreview/autoreview-chromium-extension` | https://docs.powerdevbox.com/autoreview/autoreview-chromium-extension |
| `/autoreview/autoreview-app` | https://docs.powerdevbox.com/autoreview/autoreview-app |
| `/autoreview/autoreview-power-platform-connector` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/ |
| `/autoreview/autoreview-power-platform-connector/using-connector` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/using-connector |
| `/autoreview/autoreview-power-platform-connector/info-v1-and-v2` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/info-v1-and-v2 |
| `/autoreview/autoreview-power-platform-connector/json-v1-and-v2` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/json-v1-and-v2 |
| `/autoreview/autoreview-power-platform-connector/file-v2` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/file-v2 |
| `/autoreview/autoreview-power-platform-connector/diagam-v2` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/diagam-v2 |
| `/autoreview/autoreview-power-platform-connector/http` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/http |
| `/autoreview/autoreview-power-platform-connector/file-v1` | https://docs.powerdevbox.com/autoreview/autoreview-power-platform-connector/file-v1 |
| `/autoreview/autoreview-vs-code-extension` | https://docs.powerdevbox.com/autoreview/autoreview-vs-code-extension |
| `/autoreview/api` | https://docs.powerdevbox.com/autoreview/api/ |
| `/autoreview/api/v1` | https://docs.powerdevbox.com/autoreview/api/v1/ |
| `/autoreview/api/v1/information-api-v1` | https://docs.powerdevbox.com/autoreview/api/v1/information-api-v1 |
| `/autoreview/api/v1/data-api-v1` | https://docs.powerdevbox.com/autoreview/api/v1/data-api-v1 |
| `/autoreview/api/v1/files-api-v1` | https://docs.powerdevbox.com/autoreview/api/v1/files-api-v1 |
| `/autoreview/api/v2` | https://docs.powerdevbox.com/autoreview/api/v2/ |
| `/autoreview/api/v2/information-api-v2` | https://docs.powerdevbox.com/autoreview/api/v2/information-api-v2 |
| `/autoreview/api/v2/data-api-v2` | https://docs.powerdevbox.com/autoreview/api/v2/data-api-v2 |
| `/autoreview/api/v2/files-api-v2` | https://docs.powerdevbox.com/autoreview/api/v2/files-api-v2 |
| `/autoreview/api/v2/diagram-api-v2` | https://docs.powerdevbox.com/autoreview/api/v2/diagram-api-v2 |
| `/autoreview/menu` | https://docs.powerdevbox.com/autoreview/menu |
| `/autoreview/files` | https://docs.powerdevbox.com/autoreview/files/ |
| `/autoreview/files/review` | https://docs.powerdevbox.com/autoreview/files/review |
| `/autoreview/files/report` | https://docs.powerdevbox.com/autoreview/files/report |
| `/autoreview/files/diagram` | https://docs.powerdevbox.com/autoreview/files/diagram |
| `/autoreview/files/exceptions` | https://docs.powerdevbox.com/autoreview/files/exceptions |
| `/autoreview/files/solution` | https://docs.powerdevbox.com/autoreview/files/solution |
| `/autoreview/files/compare-with-previous` | https://docs.powerdevbox.com/autoreview/files/compare-with-previous |
| `/autoreview/files/csv-files` | https://docs.powerdevbox.com/autoreview/files/csv-files |
| `/autoreview/configs` | https://docs.powerdevbox.com/autoreview/configs/ |
| `/autoreview/configs/complexity` | https://docs.powerdevbox.com/autoreview/configs/complexity/ |
| `/autoreview/configs/complexity/complexity-default-values` | https://docs.powerdevbox.com/autoreview/configs/complexity/complexity-default-values |
| `/autoreview/configs/complexity/complexity-template` | https://docs.powerdevbox.com/autoreview/configs/complexity/complexity-template |
| `/autoreview/configs/naming-convention` | https://docs.powerdevbox.com/autoreview/configs/naming-convention/ |
| `/autoreview/configs/naming-convention/naming-convention-default-value` | https://docs.powerdevbox.com/autoreview/configs/naming-convention/naming-convention-default-value |
| `/autoreview/configs/naming-convention/naming-template` | https://docs.powerdevbox.com/autoreview/configs/naming-convention/naming-template |
| `/autoreview/configs/ratings` | https://docs.powerdevbox.com/autoreview/configs/ratings/ |
| `/autoreview/configs/ratings/ratings-default-value` | https://docs.powerdevbox.com/autoreview/configs/ratings/ratings-default-value |
| `/autoreview/configs/ratings/ratings-template` | https://docs.powerdevbox.com/autoreview/configs/ratings/ratings-template |
| `/autoreview/configs/scoring` | https://docs.powerdevbox.com/autoreview/configs/scoring/ |
| `/autoreview/configs/scoring/scoring-default-values` | https://docs.powerdevbox.com/autoreview/configs/scoring/scoring-default-values |
| `/autoreview/configs/scoring/scoring-template` | https://docs.powerdevbox.com/autoreview/configs/scoring/scoring-template |
| `/autoreview/data-json` | https://docs.powerdevbox.com/autoreview/data-json |
| `/v2-v3.2.0-update` | https://docs.powerdevbox.com/autoreview/v2-v3.2.0-update |
| `/appreview/appreview-chromium-extension` | https://docs.powerdevbox.com/appreview/ |
| `/appreview/appreview-chromium-extension/known-bugs-limitations` | https://docs.powerdevbox.com/appreview/known-bugs-limitations |
| `/appreview/appreview-chromium-extension/report-sections` | https://docs.powerdevbox.com/appreview/report-sections |
| `/appreview/appreview-chromium-extension/app-settings` | https://docs.powerdevbox.com/appreview/app-settings |
| `/appreview/appreview-chromium-extension/components` | https://docs.powerdevbox.com/appreview/components |
| `/appreview/appreview-chromium-extension/variables` | https://docs.powerdevbox.com/appreview/variables |
| `/appreview/appreview-chromium-extension/code-block` | https://docs.powerdevbox.com/appreview/code-block |
| `/appreview/appreview-chromium-extension/solution` | https://docs.powerdevbox.com/appreview/solution |
| `/appreview/appreview-chromium-extension/connections` | https://docs.powerdevbox.com/appreview/connections |
| `/appreview/appreview-chromium-extension/data-source` | https://docs.powerdevbox.com/appreview/data-source |
| `/appreview/appreview-chromium-extension/diagram` | https://docs.powerdevbox.com/appreview/diagram |
| `/appreview/appreview-chromium-extension/flags` | https://docs.powerdevbox.com/appreview/flags |
| `/web-apps/solution-explorer` | https://docs.powerdevbox.com/solution-explorer/ |
| `/web-apps/unmanaged` | https://docs.powerdevbox.com/unmanaged/ |
| `/flow-utilizer/flow-utilizer-start` | https://docs.powerdevbox.com/flow-utilizer/ |
| `/flow-utilizer/install` | https://docs.powerdevbox.com/flow-utilizer/install |
| `/flow-utilizer/flow-screen` | https://docs.powerdevbox.com/flow-utilizer/flow-screen/ |
| `/flow-utilizer/flow-screen/flow-tags` | https://docs.powerdevbox.com/flow-utilizer/flow-screen/flow-tags |
| `/flow-utilizer/flow-screen/solution-download` | https://docs.powerdevbox.com/flow-utilizer/flow-screen/solution-download |
| `/flow-utilizer/solution-screen` | https://docs.powerdevbox.com/flow-utilizer/solution-screen |
| `/flow-utilizer/charts` | https://docs.powerdevbox.com/flow-utilizer/charts |
| `/flow-utilizer/account` | https://docs.powerdevbox.com/flow-utilizer/account/ |
| `/flow-utilizer/account/account-download` | https://docs.powerdevbox.com/flow-utilizer/account/account-download |
| `/dev-tools/dataverse-erd` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/ |
| `/dev-tools/dataverse-erd/getting-started` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/getting-started |
| `/dev-tools/dataverse-erd/diagram` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/diagram |
| `/dev-tools/dataverse-erd/exports` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/exports |
| `/dev-tools/dataverse-erd/exports/security-roles` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/security-roles |
| `/dev-tools/dataverse-erd/permissions-and-data` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/permissions-and-data |
| `/dev-tools/dataverse-erd/troubleshooting` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/troubleshooting |
| `/dev-tools/power-devbox-chromium-extensions` | https://docs.powerdevbox.com/dev-tools/chrome-extensions |
| `/dev-tools/power-devbox-chromium-extensions/exception` | https://docs.powerdevbox.com/dev-tools/exception |
| `/dev-tools/power-devbox-chromium-extensions/share` | https://docs.powerdevbox.com/dev-tools/share/ |
| `/dev-tools/power-devbox-chromium-extensions/share/share-demo-videos` | https://docs.powerdevbox.com/dev-tools/share/share-demo-videos |
| `/dev-tools/power-devbox-chromium-extensions/shortcut` | https://docs.powerdevbox.com/dev-tools/shortcut |
| `/dev-tools/power-devbox-chromium-extensions/utility` | https://docs.powerdevbox.com/power-devbox-utility/ |
| `/dev-tools/power-devbox-chromium-extensions/utility/classic-ui-clipboard` | https://docs.powerdevbox.com/power-devbox-utility/classic-ui-clipboard |
| `/dev-tools/power-devbox-chromium-extensions/utility/new-ui-clipboard` | https://docs.powerdevbox.com/power-devbox-utility/new-ui-clipboard |
| `/dev-tools/power-devbox-chromium-extensions/utility/utility-demo-videos` | https://docs.powerdevbox.com/power-devbox-utility/utility-demo-videos |
| `/dev-tools/power-automate-utility-vs-code` | https://docs.powerdevbox.com/dev-tools/power-automate-utility-vs-code |

## Intermediate GitBook paths from the previous attempt

These temporary heading-derived paths appeared on the old GitBook site after the previous attempt. If links were already updated to those paths, use these replacements instead.

| Intermediate GitBook path | Final app URL |
| --- | --- |
| `/dataverse-erd/dataverse-erd` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/ |
| `/dataverse-erd/dataverse-erd/getting-started` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/getting-started |
| `/dataverse-erd/dataverse-erd/diagram` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/diagram |
| `/dataverse-erd/dataverse-erd/exports` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/exports |
| `/dataverse-erd/dataverse-erd/exports/security-roles` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/security-roles |
| `/dataverse-erd/dataverse-erd/permissions-and-data` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/permissions-and-data |
| `/dataverse-erd/dataverse-erd/troubleshooting` | https://docs.powerdevbox.com/dev-tools/dataverse-erd/troubleshooting |
| `/power-devbox-extensions/power-devbox-chromium-extensions` | https://docs.powerdevbox.com/dev-tools/chrome-extensions |
| `/power-devbox-extensions/power-devbox-chromium-extensions/exception` | https://docs.powerdevbox.com/dev-tools/exception |
| `/power-devbox-extensions/power-devbox-chromium-extensions/share` | https://docs.powerdevbox.com/dev-tools/share/ |
| `/power-devbox-extensions/power-devbox-chromium-extensions/share/share-demo-videos` | https://docs.powerdevbox.com/dev-tools/share/share-demo-videos |
| `/power-devbox-extensions/power-devbox-chromium-extensions/shortcut` | https://docs.powerdevbox.com/dev-tools/shortcut |
| `/power-devbox-extensions/power-devbox-chromium-extensions/utility` | https://docs.powerdevbox.com/power-devbox-utility/ |
| `/power-devbox-extensions/power-devbox-chromium-extensions/utility/classic-ui-clipboard` | https://docs.powerdevbox.com/power-devbox-utility/classic-ui-clipboard |
| `/power-devbox-extensions/power-devbox-chromium-extensions/utility/new-ui-clipboard` | https://docs.powerdevbox.com/power-devbox-utility/new-ui-clipboard |
| `/power-devbox-extensions/power-devbox-chromium-extensions/utility/utility-demo-videos` | https://docs.powerdevbox.com/power-devbox-utility/utility-demo-videos |
| `/power-automate-utility-vs-code/power-automate-utility-vs-code` | https://docs.powerdevbox.com/dev-tools/power-automate-utility-vs-code |

## Implementation notes

* Each new manifest entry has its own route, directory, README landing page and SUMMARY navigation. There are 12 spaces, within the current app limit.
* Inbound Markdown, HTML and GitBook directive links were rebased across the repository. Existing assets remain in the registered Power DevBox Docs space; moved pages reference those same files using relative cross-space paths. No image copies or deletions are needed.
* No automatic redirects are installed by this file. Update links on the main sites using these tables; redirect configuration is a separate host change.
* GitBook heading/group URLs generated during the unsuccessful intermediate attempt are not the canonical routes for this app. Do not reuse that old map.

# Power DevBox Docs — Path Changes

Restructure: the `Dev Tools` section of the **Power DevBox** space (`power-devbox-docs`) was split so each tool is its own top-level section. Tool folders moved out of `dev-tools/` to the root of the space.

- Commit: `13ceee8` (plus map update) in `wyattdave/docs`, branch `main`
- Two sites consume this repo — both mappings are listed below:
  1. **GitBook site** — root URL `https://docs.powerdevbox.com`. The default space (`power-devbox-docs`) is served at the site root (no space prefix). URLs follow the `SUMMARY.md` nesting hierarchy and are shown with a `.md` suffix (clean URLs without `.md` resolve to the same page — drop the extension for those).
  2. **Platform (Workers)** — `https://devbox-docs.powerdevbox.workers.dev`. Routes are `/power-devbox-docs/...` (space folder prefix), clean URLs, folder landing pages (`README.md`) served as trailing-slash routes.

## GitBook site — docs.powerdevbox.com

| Old path | New path |
| --- | --- |
| `/dev-tools/dataverse-erd.md` | `/dataverse-erd.md` |
| `/dev-tools/dataverse-erd/getting-started.md` | `/dataverse-erd/getting-started.md` |
| `/dev-tools/dataverse-erd/diagram.md` | `/dataverse-erd/diagram.md` |
| `/dev-tools/dataverse-erd/exports.md` | `/dataverse-erd/exports.md` |
| `/dev-tools/dataverse-erd/exports/security-roles.md` | `/dataverse-erd/exports/security-roles.md` |
| `/dev-tools/dataverse-erd/permissions-and-data.md` | `/dataverse-erd/permissions-and-data.md` |
| `/dev-tools/dataverse-erd/troubleshooting.md` | `/dataverse-erd/troubleshooting.md` |
| `/dev-tools/power-devbox-chromium-extensions.md` | `/power-devbox-chromium-extensions.md` |
| `/dev-tools/power-devbox-chromium-extensions/exception.md` | `/power-devbox-chromium-extensions/exception.md` |
| `/dev-tools/power-devbox-chromium-extensions/share.md` | `/power-devbox-chromium-extensions/share.md` |
| `/dev-tools/power-devbox-chromium-extensions/share/share-demo-videos.md` | `/power-devbox-chromium-extensions/share/share-demo-videos.md` |
| `/dev-tools/power-devbox-chromium-extensions/shortcut.md` | `/power-devbox-chromium-extensions/shortcut.md` |
| `/dev-tools/power-devbox-chromium-extensions/utility.md` | `/power-devbox-chromium-extensions/utility.md` |
| `/dev-tools/power-devbox-chromium-extensions/utility/classic-ui-clipboard.md` | `/power-devbox-chromium-extensions/utility/classic-ui-clipboard.md` |
| `/dev-tools/power-devbox-chromium-extensions/utility/new-ui-clipboard.md` | `/power-devbox-chromium-extensions/utility/new-ui-clipboard.md` |
| `/dev-tools/power-devbox-chromium-extensions/utility/utility-demo-videos.md` | `/power-devbox-chromium-extensions/utility/utility-demo-videos.md` |
| `/dev-tools/power-automate-utility-vs-code.md` | `/power-automate-utility-vs-code.md` |

### Bulk rule (GitBook)

Every removed URL follows the same pattern — strip the `dev-tools/` segment:

```
/dev-tools/<tool-path>  →  /<tool-path>
```

where `<tool-path>` starts with one of: `dataverse-erd/`, `power-devbox-chromium-extensions/`, `power-automate-utility-vs-code`. This applies to both the `.md` and clean-URL forms.

## Platform (Workers) — devbox-docs.powerdevbox.workers.dev

| Old path | New path |
| --- | --- |
| `/power-devbox-docs/dev-tools/dataverse-erd/` | `/power-devbox-docs/dataverse-erd/` |
| `/power-devbox-docs/dev-tools/dataverse-erd/getting-started` | `/power-devbox-docs/dataverse-erd/getting-started` |
| `/power-devbox-docs/dev-tools/dataverse-erd/diagram` | `/power-devbox-docs/dataverse-erd/diagram` |
| `/power-devbox-docs/dev-tools/dataverse-erd/exports` | `/power-devbox-docs/dataverse-erd/exports` |
| `/power-devbox-docs/dev-tools/dataverse-erd/security-roles` | `/power-devbox-docs/dataverse-erd/security-roles` |
| `/power-devbox-docs/dev-tools/dataverse-erd/permissions-and-data` | `/power-devbox-docs/dataverse-erd/permissions-and-data` |
| `/power-devbox-docs/dev-tools/dataverse-erd/troubleshooting` | `/power-devbox-docs/dataverse-erd/troubleshooting` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/` | `/power-devbox-docs/power-devbox-chromium-extensions/` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/exception` | `/power-devbox-docs/power-devbox-chromium-extensions/exception` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/share/` | `/power-devbox-docs/power-devbox-chromium-extensions/share/` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/share/share-demo-videos` | `/power-devbox-docs/power-devbox-chromium-extensions/share/share-demo-videos` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/shortcut` | `/power-devbox-docs/power-devbox-chromium-extensions/shortcut` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/` | `/power-devbox-docs/power-devbox-chromium-extensions/utility/` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/classic-ui-clipboard` | `/power-devbox-docs/power-devbox-chromium-extensions/utility/classic-ui-clipboard` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/new-ui-clipboard` | `/power-devbox-docs/power-devbox-chromium-extensions/utility/new-ui-clipboard` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/utility-demo-videos` | `/power-devbox-docs/power-devbox-chromium-extensions/utility/utility-demo-videos` |
| `/power-devbox-docs/dev-tools/power-automate-utility-vs-code` | `/power-devbox-docs/power-automate-utility-vs-code` |

### Bulk rule (Workers)

```
/power-devbox-docs/dev-tools/<tool-path>  →  /power-devbox-docs/<tool-path>
```

Note: on the Workers platform, `security-roles` sits beside `exports` (route reflects the file path), whereas on GitBook it appears under `/exports/security-roles.md` (route reflects SUMMARY nesting).

## Notes

- Sidebar structure changed: `## Dev Tools` in `power-devbox-docs/SUMMARY.md` was replaced with three top-level sections — `## Dataverse ERD`, `## Power DevBox Extensions`, `## Power Automate Utility VS Code`.
- Inbound links updated in this repo: `power-devbox-docs/SUMMARY.md` and `power-devbox-docs/README.md` (landing-page card links).
- Relative asset links inside the moved pages were reduced by one `../` level (`../../.gitbook/` → `../.gitbook/`, `../../../.gitbook/` → `../../.gitbook/`) so they still resolve to `power-devbox-docs/.gitbook/assets/`.
- The GitBook site syncs from GitHub with a delay; until it re-syncs, the old `/dev-tools/...` URLs remain live and the new ones 404. Git sync moves do not create GitBook redirects automatically — add redirects in GitBook site settings using the tables above if old links must keep working.

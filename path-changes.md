# Power DevBox Docs — Path Changes

Restructure: the `Dev Tools` section of the **Power DevBox** space (`power-devbox-docs`) was split so each tool is its own top-level section. Tool folders moved out of `dev-tools/` to the root of the space.

- Root URL: `https://docs.powerdevbox.com`
- All paths below are relative to that root (space prefix `power-devbox-docs/` is unchanged).
- Folder landing pages (`README.md`) are served as trailing-slash routes — no `README.md` or `.md` extension in the URL.
- Applies to the published host at `https://docs.powerdevbox.com` (previously `https://devbox-docs.powerdevbox.workers.dev`).

## Dataverse ERD

| Old path | New path |
| --- | --- |
| `/power-devbox-docs/dev-tools/dataverse-erd/` | `/power-devbox-docs/dataverse-erd/` |
| `/power-devbox-docs/dev-tools/dataverse-erd/getting-started` | `/power-devbox-docs/dataverse-erd/getting-started` |
| `/power-devbox-docs/dev-tools/dataverse-erd/diagram` | `/power-devbox-docs/dataverse-erd/diagram` |
| `/power-devbox-docs/dev-tools/dataverse-erd/exports` | `/power-devbox-docs/dataverse-erd/exports` |
| `/power-devbox-docs/dev-tools/dataverse-erd/security-roles` | `/power-devbox-docs/dataverse-erd/security-roles` |
| `/power-devbox-docs/dev-tools/dataverse-erd/permissions-and-data` | `/power-devbox-docs/dataverse-erd/permissions-and-data` |
| `/power-devbox-docs/dev-tools/dataverse-erd/troubleshooting` | `/power-devbox-docs/dataverse-erd/troubleshooting` |

## Power DevBox Extensions

| Old path | New path |
| --- | --- |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/` | `/power-devbox-docs/power-devbox-chromium-extensions/` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/exception` | `/power-devbox-docs/power-devbox-chromium-extensions/exception` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/share/` | `/power-devbox-docs/power-devbox-chromium-extensions/share/` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/share/share-demo-videos` | `/power-devbox-docs/power-devbox-chromium-extensions/share/share-demo-videos` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/shortcut` | `/power-devbox-docs/power-devbox-chromium-extensions/shortcut` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/` | `/power-devbox-docs/power-devbox-chromium-extensions/utility/` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/classic-ui-clipboard` | `/power-devbox-docs/power-devbox-chromium-extensions/utility/classic-ui-clipboard` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/new-ui-clipboard` | `/power-devbox-docs/power-devbox-chromium-extensions/utility/new-ui-clipboard` |
| `/power-devbox-docs/dev-tools/power-devbox-chromium-extensions/utility/utility-demo-videos` | `/power-devbox-docs/power-devbox-chromium-extensions/utility/utility-demo-videos` |

## Power Automate Utility VS Code

| Old path | New path |
| --- | --- |
| `/power-devbox-docs/dev-tools/power-automate-utility-vs-code` | `/power-devbox-docs/power-automate-utility-vs-code` |

## Bulk redirect rule

Every removed URL followed the same pattern, so a single rule covers all 18 pages:

```
/power-devbox-docs/dev-tools/<tool-path>  →  /power-devbox-docs/<tool-path>
```

where `<tool-path>` starts with one of: `dataverse-erd/`, `power-devbox-chromium-extensions/`, or `power-automate-utility-vs-code`.

## Notes

- Sidebar structure changed: `## Dev Tools` in `power-devbox-docs/SUMMARY.md` was replaced with three top-level sections — `## Dataverse ERD`, `## Power DevBox Extensions`, `## Power Automate Utility VS Code`.
- Inbound links updated in this repo: `power-devbox-docs/SUMMARY.md` and `power-devbox-docs/README.md` (landing-page card links).
- Relative asset links inside the moved pages (`../../.gitbook/assets/...`, `../../../.gitbook/assets/...`) still resolve correctly because each tool moved up exactly one directory level, preserving page depth.

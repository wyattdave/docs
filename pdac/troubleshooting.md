# Troubleshooting

Start by recording the extension version, browser/version, section, selected date bounds, and the exact non-sensitive error. Reproduce in a test environment where possible; do not experiment with destructive actions to diagnose a read failure.

## The extension will not load

Confirm that the repository ZIP is extracted and **Load unpacked** points to `chrome-ext`, not the ZIP or repository root. Use a supported browser and check organizational Developer mode restrictions. After updating files, **Reload** the extension and reopen its app tab.

## Sign-in fails or shows localhost

The extension briefly uses a redirect to `http://localhost:5500/`; no listener or Node service is required. A transient connection-refused page can appear while the tab URL is captured.

If sign-in does not finish, keep the authentication tab open, complete organizational requirements, and try **Sign in different account**. The flow times out after two minutes or fails if its tab closes prematurely. Preserve the Microsoft error text but never publish the full redirect URL, authorization code, or tokens.

## No environments or no organization URL

Check the header account and select **Load environments** in Settings. Confirm actual access in Microsoft's portals. Check environment filters/visibility and whether the environment has a Dataverse database. An environment without a database cannot supply ordinary Dataverse table/role data.

## A button is disabled

Most actions require sign-in, environment selection, a loaded list, and a selected record. Imports additionally requires an analyzed ZIP, selected target, and prepared mappings. Report downloads require completed files; Charts and Trends need report data. A clean unsigned-in screen matching the guide's screenshots is expected to have disabled controls.

## A report or dashboard is empty

Check each report card's own environment selection, completion/error status, date range, and inventory filters. Enable **Enable trend data to be saved** for future historical snapshots. Charts' latest data and Trends' saved history are not the same thing. Scheduled event/session/run reports exclude today's partial activity.

Older totals may lack daily record inventories. A labelled latest-inventory fallback is not an exact historic record list. Session drilldowns can no longer retrieve expired/deleted Dataverse sessions.

## Scheduled reports did not run

Confirm the daily toggle, selected environments, valid authentication, and that the browser was running. PDAC checks at startup and every five minutes; it is not an always-on service when Chrome/Edge is fully closed. Weekly tracking is a separate switch with an hourly check. See [Scheduling](reports/scheduling.md).

## A completed file did not download

Reopen Reports and use the latest cached download links. Auto-download is per report/account/day and occurs on UI load; it is not a promise of a background disk download with no UI. Check browser download prompts/settings and the Downloads list before rerunning the report.

## A connection does not appear after creation

Complete the Power Apps flow, then refresh the component manager or **Refresh target** in Imports. Check the account, target environment, and connector compatibility. The extension does not use the Node CLI's connection-creation environment variable.

## Audit says Unavailable, Error, or Fail

Unavailable is not Disabled. Error can indicate permissions, authentication, endpoint changes, or throttling. Section Fail rates consistency, not compliance. Review sources, missing fields, collected/selected counts, and [audit limitations](environment-audit/checks.md). Updated audit host permissions may require extension reload/reapproval.

## Role upload or import affects an unexpected target

Stop before submitting any further writes. Review file-embedded role IDs, header account/environment, Imports' separate target, and prepared mappings. Preserve backups/results. Do not assume an operation rolled itself back; verify the actual state through Microsoft tools and follow your recovery procedure.

## Get help

[Open a PDAC issue](https://github.com/wyattdave/pdac/issues) with a minimal reproduction, expected/actual behavior, version, and redacted error. Remove tenant/user identities, credentials, solution secrets, and transcript content from attachments. Never upload raw browser-profile data or authentication traces to a public issue.

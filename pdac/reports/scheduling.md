# Daily scheduling and downloads

The Chrome extension runs scheduled reporting through its background service worker and browser alarms. There is no Node server or Windows task to configure.

## Enable daily runs

1. First complete a small manual run in [Reports](README.md).
2. Select the intended environments in **each** report card you want scheduled.
3. Configure the report's date range or solution inventory filters.
4. Turn on **Run daily reports in the background**.
5. Independently turn on **Enable trend data to be saved** if you want historical totals.
6. Check the queue/downloads after the next due run.

PDAC checks at startup, after settings changes, and every five minutes. Each selected report is tracked independently for the day. Successful reports are not repeatedly run while another failed report is retried. Completion includes workbook creation and, when enabled, saving the trend snapshot.

{% hint style="warning" %}
Chrome or Edge must remain running. Browser alarms cannot execute while the browser is fully closed, and a sleeping or restricted browser is not an always-on reporting service. PDAC checks again when the browser starts; do not assume missed closed-browser days were each captured on schedule.
{% endhint %}

The app tab can be closed while the browser remains running. Chrome may stop and later wake the service worker between checks; it does not need to stay continuously active. Authentication and source-API permissions must still be valid when the work runs.

## Download behavior

Completed report files are cached locally and their download links are restored when you reopen PDAC. Each card displays its latest completed result only.

**Auto download when ready** is per report. When enabled, that day's cached files download once on the first UI load for that account/report. A background completion does not mean a download has already appeared in a folder while no app UI was open.

Downloads use the browser's normal mechanism. Check browser prompts, blocked/multiple-download settings, and the Downloads list if a file was generated but did not save as expected.

## Diagnose a failed schedule

1. Check the selected account, environment selections, and scheduling toggle.
2. Read the queue's error rather than repeatedly enabling/disabling the switch.
3. Reauthenticate if required and retry a manual report.
4. Use a small environment set to distinguish permissions/data problems from a large workload.
5. Confirm that completed files and trend data are present before relying on a dashboard.

Stopping daily scheduling does not erase previously saved local totals. Weekly solution tracking is a separate switch with an hourly check; see [Weekly report](weekly-report.md).

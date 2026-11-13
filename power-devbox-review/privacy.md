# Privacy and safe sharing

## Local solution processing

Solution ZIPs are read and parsed in your browser. The app does not upload solution contents for the standard review, and it does not cache your uploaded solution files for offline reopening. App assets are separate from solution contents.

This does not mean the app makes no network requests: hosted assets must load, online license checks contact Lemon Squeezy, and purchase, billing, documentation and support-related links may open external destinations.

## What persists in the browser

The workspace can retain your custom-rule library, reviewer/theme preferences, recent solution names/summary details and locally saved bug reports. License credentials are remembered only when explicitly selected. Browser origin/profile boundaries apply: these values do not automatically transfer to another browser, device or standalone tool domain.

The recent list is not a saved copy of the solution. Closing/refreshing means selecting the ZIP again. Do not treat browser storage as your only backup for custom rules.

## Custom JavaScript

Rules receive the selected section's review data. They execute in isolated, time-limited workers with network and browser-storage/DOM access blocked. Results are displayed as text. This limits access but cannot guarantee freedom from resource exhaustion or incorrect findings.

Only import trusted code. Inspect generated rules too, even when they were created using the downloadable skills. See [Input data and output contract](flags/custom-flags/data-and-output.md#isolation-and-limits).

## Before sharing an export

Review HTML reports, copied tables, downloaded JSON, screenshots and original package files for:

* Source code, prompts and instructions.
* Tenant/environment identifiers, URLs, email addresses and internal names.
* Environment-variable defaults/values and other configuration included in the package.
* Connection/reference details and any sensitive text placed in descriptions or notes.

Redact or minimise data before sharing externally. Sending section JSON to an AI assistant is a separate transfer governed by that assistant's service and your organisation's policy; it is not covered by the reviewer's local-only parsing.

## Bug reports and shared devices

Bug reports are saved locally until you download and send them. The app does not attach solution files or keys automatically, but your typed description can still contain sensitive information.

On shared devices, leave Remember key unchecked, avoid persistent rule/report data containing sensitive text, and follow your organisation's browser-profile policy. Export useful custom rules before any deliberate site-data cleanup.

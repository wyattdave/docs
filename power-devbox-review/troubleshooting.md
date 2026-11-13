# Troubleshooting

## The ZIP will not load

Use a managed or unmanaged **Power Platform solution export**, not an arbitrary ZIP, a standalone flow export or a single extracted file. Export it again if integrity checks fail. The app enforces archive count/size/depth limits to reduce resource exhaustion; do not bypass those checks by modifying the app.

Read the loading-stage message to identify whether failure happened during ZIP reading, integrity checks, parsing or reviewer preparation. Keep the original package unchanged for comparison with a fresh export.

## One reviewer is empty or failed

First confirm the solution actually contains that component type. A flow-only solution need not populate AppReview or CopilotReview. Check Home and Solution inventories.

If a reviewer reports a preparation failure, use its **Retry** action. The workspace retains the loaded solution so you do not need to select the ZIP again just to retry that reviewer. Other reviewers can remain usable. If the issue repeats, inspect the raw package and record the failing reviewer/version without publicly sharing the whole solution.

## A value is blank, undefined or not specified

The export may omit the value or use a format the parser does not fully resolve. Confirm in **Solution files** and the relevant downloaded JSON. Do not substitute a guessed live-environment value or interpret missing configuration as runtime evidence.

## Custom flags or comparison are locked

Standard review remains free. Open Settings and activate/validate the correct Power DevBox Pro key online. Check product, status, expiry and device activation. A remembered key, edited local storage or cached app assets is not a valid offline entitlement.

## A flag produces no results

Check that it is enabled, assigned to the intended section and saved. Confirm a solution/context of that type is loaded, then **Run all flags**. Clear report filters and inspect execution errors.

An empty array or `Pass: true` is a pass; it is not displayed. AppReview field names are capitalised. Shared solution fields are absent from Apps/Automate/Copilot inputs. Use current **Download section JSON**, not only an old standalone schema.

## Imported rules fail

Verify that the file is an array of rules, not review data, findings or a skill ZIP. Legacy entries without sections need the correct section selected during import. A same-section/name import replaces the existing rule, so restore from your exported backup if needed.

Solution-key migration does not translate every nested field. Split mixed-scope checks and retest against each current section. See [Import, export and migration](flags/custom-flags/import-export.md).

## Comparison rejects the file

Load the newer export first and select an older numeric version of the same unique solution name through Compare. Selecting an older ZIP as the main solution simply replaces the baseline; it does not start comparison. See [Compare solution versions](comparing-versions.md).

## A file will not preview

Large, binary or unrecognised files intentionally do not show a text preview. Use **Download file** and an appropriate local viewer. Filename filtering searches paths, not the content of each entry.

## Installation or updates seem stuck

Use HTTPS and a supporting browser. An already installed app or a browser without an install prompt can hide the button. Close every app window before reopening online for updates. Back up custom rules before clearing site data.

## Create a useful bug report

In Settings, record the workspace version, browser, affected section, loading stage, exact visible error and short reproduction steps. State whether a synthetic/minimal export reproduces the issue. Avoid credentials and customer data.

Save the report, **download it**, and send it to support yourself. Saving locally is not submission. Keep a redacted screenshot if useful; never assume the report includes your solution automatically.

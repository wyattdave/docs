# Navigation, filters and exports

## Workspace and reviewer navigation

The outer sidebar switches between Home, the three reviewers, Solution, Flag report, Custom flags and Settings. The bottom solution button selects a ZIP; the moon/sun button changes the shared light/dark theme.

Inside a reviewer, the workspace sidebar normally becomes an **icon rail** to leave room for the reviewer's own menu. Hover an icon for its label, or use **Expand navigation** near the top. On narrower windows, collapse is also automatic. AppReview uses purple accents, AutoReview blue and CopilotReview teal.

Reviewers retain their own component lists and tabs. Switching reviewer does not reload the ZIP. In views with multiple tabs, select the relevant tab before filtering, copying or exporting.

## Shared header actions

{% hint style="info" %}
**Power DevBox Pro required:** Compare, Custom flag report and Manage custom flags need a validated license. Standard reviewer HTML/copy/data exports remain free. [Buy a license](https://power-devbox.lemonsqueezy.com/checkout/buy/729d48f6-cc59-477e-a601-ca99100ffeb3).
{% endhint %}

Each reviewer header provides:

| Action | Purpose |
| --- | --- |
| **Download as HTML** | Download the current view as an HTML report. |
| **Copy** | Copy the current view; the format depends on the reviewer and its preferences. AppReview labels this **Copy as Markdown**. |
| **Compare with an older version** | Choose an older ZIP for this reviewer's comparison; requires Pro. |
| **Custom flag report** | Open findings scoped to the current app, flow or agent. Flow Overview opens all flow findings. Requires Pro. |
| **More actions → Manage custom flags** | Open the central library filtered to this reviewer; requires Pro. |
| **More actions → Download review data (JSON)** | Download the reviewer's input-data contexts for analysis or authoring rules. |
| **More actions → Documentation** | Open that reviewer's documentation destination in a new tab. These destinations may still point to the standalone documentation. |

## Search and filters

There is no single query language for the entire workspace:

* **AppReview:** use the header search/filter when it is available. Code search and table filtering depend on the current view. A column expression such as `Name = Button1` is useful in a matching table.
* **AutoReview:** **Search flows** narrows the flow menu; the header filter works on the current review table. For example, `Name = Compose` targets an action name.
* **CopilotReview:** the header searches agents/components or filters the active table. Use visible column names and the offered operator suggestions.
* **Solution files:** the filename/path filter narrows the package tree.
* **Custom flags:** name search, section and enabled/disabled filters combine.
* **Flag report:** choose a section and use text search to narrow findings.

Clear the search text and apply it again where the view has an apply button. A filter hides rows; it does not remove components or disable rules.

## Exports

Choose exports according to the job:

| Export | Where | What to expect |
| --- | --- | --- |
| Current-view HTML / copy | Reviewer header | Human-readable evidence from the selected view. Check the output before sharing. |
| App report | AppReview **Export Report** | Consolidated report excluding the Code Block and Parameters views. Export those separately when needed. |
| Reviewer data JSON | Reviewer **More actions** | Data contexts for that reviewer, not the original ZIP. |
| Shared solution JSON | **Solution → Download JSON** | Shared metadata and component inventories. |
| Rule library JSON | **Custom flags → Export JSON** | Executable rule definitions; Pro required. |
| Findings JSON | **Flag report → Export report** | Solution identity, generation time, section totals, findings and execution errors; Pro required. |
| Original package entry | **Solution → Solution files → Download file** | The selected file's original bytes. |

Review data, rules and findings are **different files**. Importing review data into the custom-flag library will not create rules. Exported reports can contain source, URLs, IDs and configuration; follow [safe-sharing guidance](privacy.md#before-sharing-an-export).

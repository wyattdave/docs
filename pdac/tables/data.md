# Browse and query table data

Open **Tables**, load and select a table, then select **Open data**. The data browser requests readable scalar columns using the signed-in account's permissions; it is not an unrestricted Dataverse record editor.

## Paging

* **First**, **Previous**, and **Next** navigate 100-row pages.
* **Last** follows successive Dataverse continuation pages. On a large table this can make many API requests rather than jumping directly to a known final page.
* **Stop at this page** stops that traversal after the current request.
* Only the current page's record rows are retained in the viewer.
* **Refresh page** reloads the current query page.

## Filter and sort at the API

1. Expand **Filter & sort at the API**.
2. Select **Add filter**, choose a column and operator, and enter its raw API value.
3. Add further filters if needed. They are combined with **AND**, not OR.
4. Choose **Sort by** and **Direction**.
5. Select **Apply query**. Clicking a sortable column heading also queries Dataverse.

| Data type | Value to use |
| --- | --- |
| Choice | Numeric option value, not the display label |
| Boolean | `true` or `false` |
| Lookup | Record GUID |
| Date/time | ISO date or timestamp with a timezone |
| Empty value | The **Is empty (null)** operator, not the text `null` |

These filters apply to the API query, not only the currently visible rows. Use **Clear filters & sort** to reset the controls, then apply the intended query.

## Show or hide columns

Expand **Show / hide columns** and choose the fields to display. Hiding a column makes no API call. Preferences save locally per table and environment and are restored on reopening.

If a newly shown column was not fetched, its cells say **Not loaded · Apply query**. Apply the query to request it. PDAC always requests record IDs and required flow-control fields; other requests follow the active column selection. Paging/refresh keep that selection until the query is reapplied.

## Supported changes

* In **Environment Variable Value** (`environmentvariablevalue`), **Edit value** updates an existing value. Empty string and **Set to null** are distinct.
* In **Process / Workflow** (`workflow`), cloud flow rows offer **Turn on / Turn off** with a review/confirmation step. Other process records remain read-only.

Writes use record-version checks where the table supports optimistic concurrency. Otherwise, a warning explains that PDAC can recheck before saving but cannot detect another update occurring during the save. A successful write reloads page one because the record may move under the active filter/sort.

If the account or environment changes, close and reopen the browser for the new context. For creation of a variable value when only a default exists, use the [component manager](../solutions/component-actions.md), not this existing-row editor.

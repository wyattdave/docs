# Security role permissions

Export a table-permissions workbook for security roles included in the selected solution. Use it as supporting material for a design or security review, not as a user's effective-access report.

## Export the workbook

1. [Create the diagram](getting-started.md) and wait for **Checking for security roles...** to finish.
2. Look for **Role Excel** for one role, or **Roles Excel (n)** for multiple roles.
3. Select the button. The viewer shows **Building role permissions workbook...** while it retrieves privilege metadata.
4. Open the downloaded `-role-permissions.xlsx` file.

The workbook has one worksheet per discovered role. Worksheet names are shortened and sanitized for Excel. Each has a frozen header row and filters.

## Read the permissions

Each row identifies the **Role Name**, **Table**, **Logical Name** and **Record Owner**, followed by:

* **Create**
* **Read**
* **Update**
* **Delete**
* **Share**
* **Assign (Reassign)**
* **Append**
* **Append To**

Privilege depths are converted to short scope labels:

| Value | Meaning |
| --- | --- |
| `none` | No assigned scope represented for that table privilege. |
| `user` | Basic / user-level depth. |
| `business` | Local / business-unit depth. |
| `parent` | Deep / parent-and-child-business-unit depth. |
| `org` | Global / organization-level depth. |
| `recordfilter` | RecordFilter depth, when returned. |
| `N/A` | The exporter did not find a matching privilege definition for that table and operation. |

`N/A` is not the same as proof of denied access. Confirm important findings in Dataverse's security-role editor.

{% hint style="warning" %}
**Version 1.0.0 limitation:** in the reviewed public source, a numeric privilege depth of `0` (Basic) is treated as absent before scope conversion. Basic permissions returned in that form can therefore appear as `none`, or a table with only Basic permissions can be omitted. Verify user-level permissions directly in Dataverse; do not rely on this workbook alone to conclude that access is missing.
{% endhint %}

## What is included?

* **Roles:** solution security-role components, not every role in the environment.
* **Tables:** the exporter reads environment table metadata, so a selected role's sheet can include tables **outside the diagram or selected solution**.
* **Rows:** only tables where the exporter finds at least one assigned table permission. Tables with ownership type `None` and intersect tables are excluded.
* **Permissions:** the eight table operations listed above, not a complete export of every miscellaneous privilege.

{% hint style="warning" %}
**Not an effective-access calculation.** A user's access can also depend on other roles, teams, ownership, sharing, hierarchy and field security. This workbook does not combine those factors or prove that a user can access a particular record. Validate security decisions in Dataverse.
{% endhint %}

## If the button is missing

The button remains hidden if no roles were found. This can mean there are no security-role components in the solution, or role discovery could not read them. The absence of the button does not prove the environment has no roles.

Ask an administrator to confirm that the expected roles are included in this solution and readable by your account. If role retrieval fails, check [Troubleshooting](troubleshooting.md); never resolve it by sharing a bearer token.

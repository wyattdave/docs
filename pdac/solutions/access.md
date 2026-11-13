# Share components and change ownership

**Share components** and **Change component owner** operate across the selected solution's compatible components. They do not share or reassign the solution record itself, and they are different from a single component's Share dialog.

## Before you start

* Use disposable components first and confirm you have the required privileges.
* Identify the recipient by user email or exact team name.
* For ownership changes, the user must be enabled, or the team must be owner-capable.
* Review dependencies and make a change plan. The operation is **not atomic** and does not roll back earlier successful changes if a later update fails.

## Share compatible components

1. In **Solutions**, load and select the solution.
2. Select **Share components**.
3. Read the scope and dependency warning.
4. Choose **User** or **Team** and enter the recipient.
5. Review **Permissions**. The default is `ReadAccess,WriteAccess,AppendAccess,AppendToAccess,ShareAccess`; narrow it when appropriate for your use case.
6. Select **Share all compatible components** only when ready to apply the changes.
7. Review every result category, not just the success count, and verify recipient access separately.

## Change ownership

Select **Change component owner**, choose the eligible recipient, and review the dialog before submitting. Discovery completes before writes begin. Read the final results for successful changes, failures, unsupported components, inherited/role-controlled records, and anything left unprocessed.

## What is included?

Supported discovery covers environment-variable definitions, connection references, custom connectors, workflows, prompts/AI models, and Copilot Studio agents. Agent discovery includes topics, collections, and linked authoring dependencies. Those dependencies can be **outside the solution or used elsewhere**. Discovery deduplicates records and excludes transcripts/runtime data.

Environment-variable values inherit definition permissions. Organization-owned records cannot be individually shared or reassigned; sharing checks the recipient's table Read privileges instead. Other component types are reported as unsupported, not treated as successfully changed.

## What this does not grant

It does not automatically configure tenant/environment membership, licensing, all security-role privileges, flow run/co-owner product settings, connection credentials, channels, or external-source access. Effective Dataverse sharing is verified, but end-to-end product access still needs a recipient test.

If part of an operation fails, preserve the result details before retrying. Review which changes already succeeded; do not assume that a failure left the environment unchanged.

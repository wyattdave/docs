# Component actions

Component managers are reached from **Solutions → List components**, not from a separate navigation tab. Load the solution, select a supported component's management action, and review the dialog's details and notes before saving.

## Environment variables

1. Open the variable's manager.
2. Confirm its schema name, type, value source, and default.
3. Enter the intended **Current value**.
4. Select **Save value**.

PDAC updates the related value row or creates one if only a definition/default exists. This is a target-environment value change, not a change to a deployment-settings file. Avoid exposing secrets in screenshots or exported documentation.

## Connection references

1. Open the connection reference.
2. Check its connector and current connection.
3. Choose an existing matching connection and select **Switch connection**.
4. If none exists, select **Create connection**, complete the Power Apps browser flow, then return and select **Refresh**.
5. Select and switch to the new matching connection if it has not already been applied.

In the **extension**, connection creation opens Power Apps. Node-specific CLI settings and environment variables are not required. A completed browser flow does not mean the reference has automatically switched; verify the current connection.

## Flows

The flow manager displays its state and whether a manual trigger was detected. **Turn on / Turn off** writes the Dataverse workflow state. Review the target carefully and check the resulting state after the action.

Manual-trigger connection references can be inspected, but **run-only users and manual-trigger connection mode are read-only in PDAC**. Manage those through the appropriate Power Automate tools; sharing a Dataverse workflow row is not equivalent to configuring run-only access.

## Share one supported component

1. Open its manager and review the available **Role** choices.
2. Type at least two characters in **Find users or teams**.
3. Select the intended principals from the results.
4. Check the selected recipient chips and remove accidental selections.
5. Select **Share** and read the result.

Supported types include flows, canvas apps, code apps, and agents/agent components where the dialog offers sharing. Agents can offer an analytics-viewer role; Dataverse read access alone does not guarantee access to every Copilot Studio analytics feature.

{% hint style="warning" %}
These are live changes using your account. Recipients still need environment access, licensing, security roles, and any separate connection or data-source permissions. There is no general-purpose editor for every solution component, and unsupported actions are not silently performed.
{% endhint %}

For operations covering the whole solution, see [Share components and change ownership](access.md).

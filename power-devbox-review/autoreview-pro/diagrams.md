# Flow diagrams

Flow diagrams turn an exported flow definition into a structural view of its trigger, actions and branches.

## Open a diagram

1. Open **AutoReview Pro** and select a flow.
2. Choose **Diagram** from the flow's actions.
3. Follow the trigger through actions, conditions and containers.
4. Return to the review/action detail to check the exact configuration behind a node.

Use the diagram to spot deep nesting, repeated structures and surprising branch placement. Review exception paths alongside run-after settings: the visual arrangement alone is not a guarantee that a path runs under the intended conditions.

## Flag highlighting

With Pro custom findings available, **Settings → Reviewer preferences → AutoReview Pro → Highlight Flagged Actions on Diagram** controls highlighting. A finding must map to the relevant flow/action for that action to be highlighted. A solution-level warning or a finding whose component name does not match an action may still appear in the report without highlighting a node.

## Comparison diagrams

After [comparing with an older version](../comparing-versions.md), AutoReview provides its changed-flow comparison views and diagrams. Inspect the associated action details before approving a change. Formatting or a definition difference does not by itself measure impact on execution time or API usage.

## Limits

Diagrams describe the **exported definition**, not run history. They cannot tell you which branch a real run followed, its duration, returned values or failure rate. Keep the definition, the diagram and any runtime evidence separate in your review notes.

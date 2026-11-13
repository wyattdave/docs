# Instructions, topics and skills

## Instructions

Open **Instructions** to review the agent's instruction text and available response instructions. Check that purpose, boundaries, escalation and use of capabilities are clear. Inspect referenced components when instructions refer to tools, topics or other exported resources.

An instruction being present does not prove that it is effective or that the model follows it in every conversation. Review the surrounding authentication/capability settings and test important behaviours separately.

## Topics

**Topics** lists the agent's exported topics with information such as active/system status, trigger, size and structure. Select a topic for details; use its diagram or YAML view where available.

Review trigger phrases/conditions, input/output expectations, node structure, redirects, variable use and calls to tools/flows. Investigate broken references and parse errors before interpreting incomplete counts as a complete review.

**Show System Topics** in reviewer preferences controls inclusion of default/system content in the displayed topic list. A team's maker-content rule should explicitly decide whether system/default topics belong in its scope instead of assuming every topic was authored by that team.

## Skills

When the agent has exported skill content or uses the relevant harness, **Skills** exposes the available skill packages and files. Open a skill to inspect the packaged instructions and available file/data views.

Check for a meaningful `SKILL.md`, supporting files that are actually needed and unwanted generated/cache files. A skill package in an agent export is not the same thing as the **downloadable AI authoring skills for writing review flags**. Those are provided separately on [Download AI authoring skills](../flags/custom-flags/ai-skills.md).

## Source-level review limits

The reviewer does not execute topics or skills, run an evaluation suite or obtain conversation transcripts. Static text checks can identify suspicious references or conventions, but cannot establish prompt quality, safety or resolution rate by themselves.

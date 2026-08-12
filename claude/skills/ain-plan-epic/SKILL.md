---
name: ain-plan-epic
description: Plan a new epic in an AI-native repo, following docs/rules.md.
arguments: [description]
argument-hint: <epic-description>
disable-model-invocation: true
---

Plan a new epic based on this description: $ARGUMENTS

1. Read `docs/rules.md` in the current repo and follow its epic conventions. If it is missing, tell the User and stop.
2. Explore the codebase and existing epics under `docs/epics/` as needed to ground the plan in reality.
3. Determine the next epic number `<N>` from existing `epic-<N>-*` folders, and derive a short kebab-case slug from the description.
4. Create `docs/epics/epic-<N>-<slug>/README.md` — a comprehensive but compressed rationale:
   - **What** we build and **why** (the goal, tied to the User's description).
   - **Scope** — what is in and explicitly out.
   - **Progress** — task table (empty for now, or listing tasks if the User asked to plan them too), with statuses.
   - References to any relevant research under `docs/research/`.

Do NOT plan individual tasks unless the User asked for it in the description — that is what `/ain-plan-tasks` is for.
Do NOT write any code. Do NOT touch git.

If the description is too vague to state a clear goal and scope, ask the User clarifying questions before creating anything.

When done, summarize the epic for the User: number, name, goal, scope boundaries, and suggest planning tasks as the next step.

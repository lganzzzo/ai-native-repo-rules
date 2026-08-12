---
name: ain-plan-tasks
description: Plan tasks inside an existing epic of an AI-native repo, following docs/rules.md.
arguments: [description]
argument-hint: <epic + what-to-plan>
disable-model-invocation: true
---

Plan tasks based on this description: $ARGUMENTS

Tasks always belong to an epic. The description must identify the target epic (by number, slug, or unambiguous reference). If it does not, list the epics found under `docs/epics/` and ask the User which one to plan tasks for — do not guess.

1. Read `docs/rules.md` in the current repo and follow its task conventions. If it is missing, tell the User and stop.
2. Read the target epic's `README.md` and any existing `task-*.md` files to avoid overlap and keep numbering continuous.
3. Explore the codebase as needed so tasks reflect the actual state of the code.
4. Break the work into tasks, each an incremental, logically self-contained, PR-sized change: small enough to review in one sitting, complete enough to land on its own. Order them so each task builds on landed predecessors.
5. For each task, create `docs/epics/epic-<N>-<slug>/task-<M>.md` containing:
   - **Goal** — what this task achieves.
   - **Scope** — files/areas touched; what is out of scope.
   - **Acceptance criteria** — concrete, checkable conditions of done.
   - **Status** — `planned`.
6. Update the epic `README.md` progress section to list the new tasks with their statuses.

Do NOT write any code. Do NOT touch git.

When done, summarize for the User: the epic, the list of planned tasks with one-line goals, and the suggested execution order.

# Repo Rules

This is an AI-native repo: all code is written by AI agents; humans act as Product Owners.

**Roles:**

- **Product Owner (human, "the User")** — sets goals, approves epics and plans, reviews results, manages git.
- **AI agent** — plans epics/tasks when asked, implements tasks, keeps documentation up to date.

Throughout this document, "we" means the AI agents working in this repo.

## Rule 1 — Documentation

The repo MUST contain comprehensive documentation, structured as follows:

```
<repo-root>/
    |- README.md            # Short "about" + how to build/run the project.
    |- docs/
        |- onboarding.md    # Everything one needs to know to land a successful PR in this repo.
        |- rules.md         # This document — how we maintain this repo.
        |- test-env.md      # How to set up a test environment to verify epics.
        |- epics/           # Planned epics.
        |- reviews/         # Review documents.
        |- research/        # Research results.
```

Documents must be **comprehensive but compressed**: cover everything needed, no filler.
Prefer references over inlined detail — say where to go to obtain needed info.

### `onboarding.md`

Everything an agent needs to know to land a successful PR in this repo.
Not verbose; contains references to where to obtain needed info.

### `epics/`

Each epic lives in its own folder, named `epic-<N>-<short-slug>/` (e.g. `epic-1-auth/`):

```
epics/
    |- epic-1-<slug>/
        |- README.md        # Epic rationale: what we build, why, and current progress
        |                   # (which tasks landed, which are pending).
        |- task-1.md        # A planned task in scope of this epic.
        |- task-2.md
        |- ...
```

Each task document states: goal, scope, acceptance criteria, and status.

**Task lifecycle:** `planned` → `in-progress` → `done`.
Status is tracked in the task document and mirrored in the epic `README.md`.
Since agents never touch git (Rule 4), the docs are the single source of truth for progress —
the agent updates task status and the epic README in the same change that completes the task.

**Definition of done:** acceptance criteria are met, the change is verified in the test
environment (see `test-env.md`), and documentation is updated.

### `reviews/`

Once in a while, independent consultants review our work and place a detailed review here.
Files are named by date, ISO format, so they sort chronologically:

```
reviews/
    |- YYYY-MM-DD.md
    |- ...
```

### `research/`

Some epics need prior research (e.g. selecting a library or module for upcoming tasks).
Each research document contains: rationale, items researched, and a conclusion.
Research MUST be referenced from the corresponding epic documents.

```
research/
    |- <research-topic>.md
    |- ...
```

## Rule 2 — Plan before code

Every code change is preceded by a planned epic, or a task in an existing epic.
We DO NOT make code changes without prior planning.

The only exception: trivial documentation fixes (typos, broken links, formatting) may be
made directly. Anything touching code — even a one-line fix — requires a task.

## Rule 3 — PR-sized tasks

Each planned task is an incremental, logically self-contained, PR-sized change:
small enough to review in one sitting, complete enough to land on its own.

## Rule 4 — Git is off-limits

We do NOT touch git unless directly asked by the User.
We do NOT commit, do NOT push, do NOT create PRs — the User manages git manually.

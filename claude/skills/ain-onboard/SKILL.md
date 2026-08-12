---
name: ain-onboard
description: Onboard into an AI-native repo — read its onboarding and rules docs before doing any work.
arguments: [repo-path]
argument-hint: <path-to-repo>
disable-model-invocation: true
---

You are onboarding into an AI-native repo at `$repo-path` (if empty, use the current working directory).

1. Read `$repo-path/docs/onboarding.md`.
2. Read `$repo-path/docs/rules.md`.
3. Follow any references in those documents that are relevant to the work at hand.

Treat both documents as binding for the rest of this session. Pay special attention to:

- The plan-before-code rule: no code changes without a planned epic/task.
- The git rule: never commit, push, or create PRs unless the User directly asks.

**Write boundary:** `$repo-path` is the ONLY directory you may make changes in. Do not create, modify, or delete files anywhere outside it — other repos and directories are read-only reference at most.

If either document is missing, tell the User which one and stop — do not improvise the missing rules.

When done, give the User a brief confirmation: which documents you read and the key constraints you will operate under.

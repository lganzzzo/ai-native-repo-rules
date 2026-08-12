---
name: ain-review
description: Review code, tasks, decisions, or research in an AI-native repo, following docs/rules.md.
arguments: [description]
argument-hint: <what-to-review>
disable-model-invocation: true
---

Perform a review based on this description: $ARGUMENTS

1. Read `docs/rules.md` in the current repo — it defines the conventions the subject is reviewed against. If it is missing, tell the User and stop.
2. Identify the review subject from the description: code, planned epics/tasks, a decision, research results, or documentation. If ambiguous, ask the User before proceeding.
3. Read the subject thoroughly, plus enough surrounding context (related epics, tasks, research, code) to judge it fairly. Do not review what you have not read.
4. Assess against:
   - The rules in `docs/rules.md` (structure, plan-before-code traceability, PR-sized tasks, documentation quality).
   - The subject's own stated goals and acceptance criteria, where they exist.
   - General soundness: correctness, clarity, gaps, risks.
5. Write the review to `docs/reviews/YYYY-MM-DD.md` (today's date; if a review for today already exists, append a short slug: `YYYY-MM-DD-<slug>.md`). Structure it as:
   - **Subject** — what was reviewed and at what state.
   - **Findings** — ordered most severe first; each with concrete evidence (file references) and a suggested remedy.
   - **Verdict** — overall assessment and recommended next steps.

Be a critical, independent reviewer: verify claims against the actual files rather than trusting documents' self-description. Report what is good briefly; spend the depth on problems.

Do NOT fix anything during the review — findings become tasks via normal planning. Do NOT touch git.

When done, give the User the verdict and the top findings inline, and link the review file.

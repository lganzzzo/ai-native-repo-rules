# Repo Rules

## Rule 1

Repo MUST contain comprehensive documentation.
 
### General documentation structure

```
<repo-root>/
    |- README.md                    # A short about readme + instructions how to build/run the project.
    |- docs/                        # main documentation folder
        |- onboarding.md            # A comprehensive compressed document - everything the one needs to know, to land a successful PR in this repo. 
        |- rules.md                 # this rules.md - description how we maintain this repo.
        |- test-env.md              # A comprehensive compressed document - how to setup a test env to verify epics.
        |- epics/                   # A folder with planned epics
        |- reviews/                 # A folder with reviews
        |- research/                # A folder with reasearch results
```

### `onboarding.md` document

This should be a comprehensive compressed document - everything the one needs to know, to land a successful PR in this repo.
Should not be verbose, contains references, where to go to obtain needed info.

### `epics/` folder

This folder contains planned epic folders.

```
epics/
    |- epic-1/
    |- epic-2/
    |- ...
```

Each epic consists of list of tasks. 
Epic folder has the following structure:

```
epic-1/
    |- README.md            # A comprehensive compressed document with the epic rational - what we build, why, and what is the current progress (what tasks landed, what tasks are pending).
    |- task_1.md            # A planned task in scope of this epic
    |- task_2.md            # A planned task in scope of this epic
    |- ...
```

### `reviews/` folder

This folder contains review documents.
Once in a while we ask independent consultants to review our work.- they write a detailed review
and place it here. Each review is stamped by a date.

```
reviews/
    |- <date>.md
    |- <date>.md
    |- ...
```

### `research/` folder

Some epics might need a prior research to move forward, ex.: select a library or a module to use for the next tasks.
In such cases we plan research. Each research document should contain the research rational, items researched, and conclusion.
Research then must be mentioned in corresponding epic documents.

```
reviews/
    |- <research-1>.md
    |- <research-2>.md
    |- ...
```

## Rule 2

Each code change in the repo is preceded by a planned epic or a task in the existing epic.
We DO NOT make any code changes without prior planning.

## Rule 3

Each planned task in the epic is a PR-sized incremental, logical change.

## Rule 4

We do NOT ever touch git, unless directly asked by the User.
We do NOT commit, we do NOT push, we do NOT create any PRs.- user manages git manually.

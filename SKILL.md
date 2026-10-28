---
name: test-gap-finder
description: Identify missing or weak tests around recent code changes, risky modules, bug fixes, refactors, and public APIs. Use when preparing a PR, modifying unfamiliar code, fixing bugs, or deciding which unit, integration, regression, edge-case, and snapshot tests should be added or updated.
---

# Test Gap Finder

## Core Workflow

Find the smallest useful set of tests that would make a change safer. Prefer targeted, behavior-focused tests over broad test expansion.

1. Inspect the change surface: user request, issue, git diff, touched files, public APIs, data models, UI states, config, and side effects.
2. Find existing test patterns near the changed code before proposing new test structure.
3. Identify behavior that changed, behavior that should not change, and behavior that is currently untested.
4. Classify gaps by risk: regression, edge case, integration boundary, error handling, authorization, concurrency, migration, serialization, UI state, or snapshot drift.
5. Recommend the smallest test additions or updates that prove the change and protect likely breakpoints.
6. If asked to implement, add tests using local conventions and run the narrowest relevant test command first.
7. Report what is covered, what remains uncovered, and which tests should be run before merge.

## Reference Routing

Load only what matches the task:

- For reading diffs and finding impacted behavior, read `references/change-triage.md`.
- For choosing test types and gap categories, read `references/test-taxonomy.md`.
- For prioritizing what matters, read `references/gap-rubric.md`.
- For the final recommendation format, read `references/output-template.md`.
- For realistic examples, read `references/examples.md`.

## Rules

- Do not ask for exhaustive coverage when a focused regression test is enough.
- Do not invent a new test framework when the repository already has one.
- Do not update snapshots blindly. Explain what behavior the snapshot protects.
- Prefer tests that fail before the fix and pass after it when diagnosing a bug.
- Treat missing tests around security, data loss, payments, migrations, and auth as high priority.
- If test execution is blocked, still provide exact test files, cases, and commands to run.

## Output Contract

Return:

- `Change Surface`: files, APIs, flows, or behavior under review.
- `Existing Coverage`: relevant tests found or likely missing.
- `Test Gaps`: prioritized missing or weak tests.
- `Recommended Tests`: specific cases to add or update.
- `Commands`: focused test commands to run.
- `Residual Risk`: uncovered paths or assumptions.

# Change Triage

Use this to understand what changed before recommending tests.

## Inspect the Surface

Look for changed public functions, classes, routes, commands, components, schemas, migrations, jobs, configuration, branches, guards, validation rules, defaults, error paths, dependencies, external calls, file I/O, database access, network access, or background work.

Treat permissions, money, user data, concurrency, and persistence as especially important.

## Trace Impact

For each changed file, identify direct callers, downstream consumers, nearby tests, fixtures, shared helpers, API contracts, generated types, and UI states affected by loading, empty, error, disabled, and success paths.

## Existing Test Search

Search for colocated tests, test names matching changed functions or flows, fixtures using the changed model or route, snapshots covering the changed component, and integration tests that exercise the same user flow.

Prefer local naming conventions. If tests use `*.spec.ts`, do not propose `*.test.ts` unless both exist.

## Bug Fix Triage

For a bug fix, look for the exact failing scenario, the smallest reproduction case, adjacent cases that could regress, and prior tests that passed while missing the bug.

Recommend at least one regression test that would fail on the original bug.

## Refactor Triage

For a refactor, look for changed interfaces, moved files with lost tests, renamed exports with stale imports, changed initialization order or side effects, and test helpers that should be updated rather than duplicated.

Focus on characterization tests around externally observable behavior.

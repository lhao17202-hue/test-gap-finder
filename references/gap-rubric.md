# Gap Rubric

Use this to prioritize missing tests.

## High Priority

Recommend tests first when the change touches authentication, authorization, permissions, roles, sessions, tokens, payment, billing, irreversible actions, data deletion, migration, export, import, persistence, external APIs, queues, retries, webhooks, background jobs, concurrency, caching, locking, async ordering, shared mutable state, or user-visible bug fixes that lacked a regression test.

## Medium Priority

Recommend tests when the change touches public module APIs, validation, parsing, feature flags, configuration, error handling, fallback behavior, UI state transitions, cross-platform paths, locale, time, timezone, or randomness.

## Low Priority

Tests may be unnecessary or minimal when only comments or docs changed, formatting-only changes occurred, generated files changed without source behavior changes, or existing tests already cover the exact behavior and should simply be run.

## Smell Checklist

Flag weak coverage when tests only assert mocks were called, snapshots changed without behavioral assertions, error paths are missing, only happy paths exist for risky input, tests duplicate implementation details, a bug fix lacks a failing-before regression case, or new branches and feature flags have no off-state test.

## Recommendation Size

Keep recommendations practical:

- tiny change: 0-2 focused tests
- normal feature or bug fix: 2-5 tests
- risky cross-module change: prioritized list with must-have and nice-to-have groups

Avoid turning every code review into a coverage crusade.

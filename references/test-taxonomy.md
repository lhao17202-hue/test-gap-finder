# Test Taxonomy

Use this to choose the right kind of test for each gap.

## Unit Tests

Use when logic is pure or mostly isolated, branch behavior changed, or validators, parsers, formatters, calculators, mappers, reducers, and policies changed.

Good unit tests name input, expected output, and edge cases. Avoid mocking so much that the behavior under test disappears.

## Integration Tests

Use when behavior crosses module boundaries, routes, services, repositories, queues, database flows, configuration, dependency wiring, or serialization changed.

Integration tests should verify the contract between real collaborators where practical.

## Regression Tests

Use when a bug was fixed, a production incident or failing test motivated the change, or the previous suite missed the issue.

The test should fail against the buggy behavior and pass after the fix.

## Contract or API Tests

Use when public interfaces, request/response shape, generated clients, OpenAPI, GraphQL, RPC, CLI arguments, or SDK exports changed.

Cover success, validation failure, compatibility, and documented defaults.

## UI Tests

Use when user-visible rendering, interactions, loading, empty, disabled, error, success states, accessibility labels, or keyboard behavior changed.

Prefer behavior assertions over brittle structure assertions.

## Snapshot Tests

Use sparingly when output is structured and intentionally stable, or visual/serialized output is too large for clear inline assertions.

Do not rely on snapshots alone for business logic.

## Migration and Data Tests

Use when database schema, data migration, storage format, or backward compatibility changed.

Cover old data, new data, nulls/defaults, rollback assumptions, and idempotency.

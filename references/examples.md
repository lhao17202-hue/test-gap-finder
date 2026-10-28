# Examples

## Bug Fix

User:

```text
Use $test-gap-finder on this checkout before I open the PR.
```

Good output identifies the bug-fix file and exact behavior, finds nearby tests, recommends one regression test that fails on the old bug, adds edge cases only when the bug suggests them, and names the focused test command.

## API Change

User:

```text
I changed the user export endpoint to include archived users. What tests are missing?
```

Good recommendations include a success case with archived users included, a permission case if export is restricted, an empty result case, serialization field contract coverage, and a command for endpoint or integration tests.

## Refactor

User:

```text
This is supposed to be a behavior-preserving refactor. Find test gaps.
```

Good recommendations characterize public behavior before trusting internals, run existing package tests, add tests only where behavior lacks coverage, and avoid asserting private helper structure.

## UI State

User:

```text
I added a disabled state to the checkout button.
```

Good recommendations cover disabled state rendering when the form is invalid, click not submitting while disabled, accessible state staying correct, and enabled state still submitting.

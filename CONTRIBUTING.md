# Contributing

Contributions should make test-gap recommendations more accurate, practical, and easy to apply.

## Good Contributions

- Add realistic examples for common frameworks or change types
- Improve risk prioritization
- Clarify when tests are unnecessary
- Strengthen validation checks
- Add better guidance for regression, contract, UI, migration, or async tests

## Avoid

- Generic "increase coverage" advice
- Recommendations that ignore local test conventions
- Unlinked reference files
- Placeholder TODO text
- Encouraging broad test rewrites for small changes
- Snapshot updates without behavior explanation

## Workflow

1. Edit `SKILL.md`, `references/`, or `scripts/`.
2. Run:

```bash
python scripts/validate_skill.py .
```

3. Keep core routing in `SKILL.md`; move examples and detailed criteria into `references/`.

## Review Checklist

- `SKILL.md` frontmatter has only `name` and `description`
- description includes capability and trigger context
- references are linked from `SKILL.md`
- no placeholder files remain
- validator passes

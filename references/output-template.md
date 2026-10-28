# Output Template

Use this format for test gap reports.

```markdown
**Change Surface**
- `<path>`: <changed behavior or risk>

**Existing Coverage**
- `<test path>`: <what it already covers>
- Missing/unclear: <area>

**Test Gaps**
1. <priority> - <missing behavior> because <risk>
2. <priority> - <missing behavior> because <risk>

**Recommended Tests**
- Add `<test file>`: <case name and assertion>
- Update `<test file>`: <case name and assertion>

**Commands**
- `<command>`: <why this command>

**Residual Risk**
- <uncovered path, blocked execution, or assumption>
```

## Compact Variant

```markdown
Must add:
- <test case>

Should run:
- `<command>`

Already covered:
- <existing test or "not found">
```

## If Implementing Tests

After adding tests, report files changed, cases added, command results, and failures that remain unrelated or blocked.

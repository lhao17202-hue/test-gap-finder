# Test Gap Finder

Test Gap Finder is a Codex skill for identifying missing or weak tests around code changes.

It helps developers prepare safer pull requests by comparing a change surface against nearby test conventions, then recommending the smallest useful set of unit, integration, regression, contract, UI, snapshot, migration, or edge-case tests.

## Use Cases

Use this skill when you want Codex to:

- inspect a diff and find missing test coverage
- decide which tests a bug fix needs
- prepare a PR with a focused test plan
- review risky refactors for coverage gaps
- identify weak snapshot-only or mock-only tests
- recommend exact test files, cases, and commands

Example prompt:

```text
Use $test-gap-finder to inspect this diff and tell me which tests I should add before opening the PR.
```

## Skill Metadata

```yaml
name: test-gap-finder
description: Identify missing or weak tests around recent code changes, risky modules, bug fixes, refactors, and public APIs. Use when preparing a PR, modifying unfamiliar code, fixing bugs, or deciding which unit, integration, regression, edge-case, and snapshot tests should be added or updated.
```

## Repository Structure

```text
.
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
|-- references/
|   |-- change-triage.md
|   |-- examples.md
|   |-- gap-rubric.md
|   |-- output-template.md
|   `-- test-taxonomy.md
|-- scripts/
|   `-- validate_skill.py
|-- .github/
|   `-- workflows/
|       `-- validate.yml
|-- CONTRIBUTING.md
|-- LICENSE
`-- README.md
```

## Install

Clone this repository into your Codex skills directory:

```bash
git clone https://github.com/lhao17202-hue/test-gap-finder.git ~/.codex/skills/test-gap-finder
```

Windows PowerShell:

```powershell
git clone https://github.com/lhao17202-hue/test-gap-finder.git "$env:USERPROFILE\.codex\skills\test-gap-finder"
```

Restart Codex or reload skills if your environment does not detect new skills automatically.

## Validate

Run:

```bash
python scripts/validate_skill.py .
```

The validator checks required files, frontmatter, UI metadata, reference routing, unresolved placeholders, and the 350-character description limit.

## Design

The core `SKILL.md` stays concise. Diff triage, test taxonomy, gap prioritization, output formats, and examples live in `references/`.

## License

MIT

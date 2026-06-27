# Step 046 — Record the commit standards decision

**Phase:** `03-tooling-foundation`

## Purpose

Record the decision to use Conventional Commits before adding commitlint.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0008-use-conventional-commits.md <<'EOF'
# ADR-0008: Use Conventional Commits

## Status

Accepted

## Date

2026-06-26

## Context

The repository needs consistent commit messages for history, changelogs, releases, automation, and contributor clarity.

## Decision

Use Conventional Commits for all commits.

Examples:

```text
feat(cli): add moro command skeleton
docs(adr): choose biome for formatting and linting
chore(repo): add root gitignore
```

## Consequences

This supports future Changesets, release notes, changelog automation, and better repository history.

## Alternatives Considered

Informal commit messages were rejected because they weaken automation and long-term maintainability.
EOF

python - <<'PY'
from pathlib import Path
p = Path('docs/architecture/decisions/index.md')
text = p.read_text()
row = '| ADR-0008 | Use Conventional Commits | Accepted |'
if row not in text:
    p.write_text(text.rstrip() + '\n' + row + '\n')
PY
```

## Validate

```bash
grep "ADR-0008" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): adopt conventional commits"
git push
```

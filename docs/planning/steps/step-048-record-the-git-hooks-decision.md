# Step 048 — Record the Git hooks decision

**Phase:** `03-tooling-foundation`

## Purpose

Record the decision to use Lefthook before installing and configuring it.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0009-use-lefthook-for-git-hooks.md <<'EOF'
# ADR-0009: Use Lefthook for Git Hooks

## Status

Accepted

## Date

2026-06-26

## Context

The repository needs fast, local Git hooks for commit validation and pre-push checks.

## Decision

Use Lefthook as the default Git hook manager.

## Consequences

Contributors get consistent local checks before changes reach CI.

## Alternatives Considered

- simple-git-hooks: lighter, but less full-featured.
- pre-commit: powerful, but adds a Python-oriented workflow.
EOF

python - <<'PY'
from pathlib import Path
p = Path('docs/architecture/decisions/index.md')
text = p.read_text()
row = '| ADR-0009 | Use Lefthook for Git Hooks | Accepted |'
if row not in text:
    p.write_text(text.rstrip() + '\n' + row + '\n')
PY
```

## Validate

```bash
grep "ADR-0009" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose lefthook for git hooks"
git push
```

# Step 044 — Record the branching strategy decision

**Phase:** `02-documentation-foundation`

## Purpose

Document trunk-based development with GitHub Flow-style pull requests before branch protection is enabled.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0007-use-trunk-based-development-with-github-flow.md <<'EOF'
# ADR-0007: Use Trunk-Based Development with GitHub Flow

## Status

Accepted

## Date

2026-06-26

## Context

The project needs a simple branch strategy that works for a solo maintainer now and contributors later.

## Decision

Use trunk-based development with `main` as the protected trunk and short-lived GitHub Flow-style pull request branches.

## Consequences

The workflow remains simple, reviewable, and CI-friendly.

## Alternatives Considered

- Git Flow: rejected as too heavy for this project.
- Long-lived environment branches: rejected for v1.

## Follow-up Work

- Document the branch strategy.
- Enable branch protection after CI exists.
EOF

python - <<'PY'
from pathlib import Path
p = Path('docs/architecture/decisions/index.md')
text = p.read_text()
row = '| ADR-0007 | Use Trunk-Based Development with GitHub Flow | Accepted |'
if row not in text:
    p.write_text(text.rstrip() + '\n' + row + '\n')
PY
```

## Validate

```bash
grep "ADR-0007" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define branching strategy"
git push
```

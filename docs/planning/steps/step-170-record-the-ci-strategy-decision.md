# Step 170 — Record the CI strategy decision

**Phase:** `12-release-ci`

## Purpose

Record GitHub Actions as the default CI platform.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0039-use-github-actions-for-ci.md <<'EOF'
# ADR-0039: Use GitHub Actions for CI

## Status

Accepted

## Date

2026-06-26

## Context

The repository needs automated validation for pull requests and releases.

## Decision

Use GitHub Actions as the default CI platform.

## Consequences

Checks can run on pull requests, pushes, and release workflows inside GitHub.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0039 | Use GitHub Actions for CI | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0039" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose github actions for ci"
git push
```

# Step 058 — Record the dependency consistency decision

**Phase:** `03-tooling-foundation`

## Purpose

Record the decision to use Syncpack for package dependency consistency.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0012-use-syncpack-for-dependency-consistency.md <<'EOF'
# ADR-0012: Use Syncpack for Dependency Consistency

## Status

Accepted

## Date

2026-06-26

## Context

A monorepo with many packages needs consistent dependency ranges, package metadata, and dependency policy.

## Decision

Use Syncpack as the default dependency consistency tool.

## Consequences

Dependency drift becomes easier to detect and fix.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0012 | Use Syncpack for Dependency Consistency | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0012" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose syncpack for dependency consistency"
git push
```

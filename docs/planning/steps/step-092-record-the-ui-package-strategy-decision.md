# Step 092 — Record the UI package strategy decision

**Phase:** `05-shared-packages`

## Purpose

Record the shared UI package as the design-system home.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0025-use-a-shared-ui-package.md <<'EOF'
# ADR-0025: Use a Shared UI Package

## Status

Accepted

## Date

2026-06-26

## Context

The starter will include web, admin, docs, storybook, and optional app profiles.

## Decision

Use `packages/ui` as the shared UI and design-system package.

## Consequences

UI primitives and conventions can be reused across applications.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0025 | Use a Shared UI Package | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0025" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define shared ui package strategy"
git push
```

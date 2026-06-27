# Step 127 — Record the local dashboard decision

**Phase:** `08-dashboard-graphs`

## Purpose

Record the decision to include a local repository dashboard later.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0031-provide-a-local-repository-dashboard.md <<'EOF'
# ADR-0031: Provide a Local Repository Dashboard

## Status

Accepted

## Date

2026-06-26

## Context

The starter should be inspectable without requiring users to memorize every CLI command.

## Decision

Provide a future local dashboard through `moro dashboard`.

## Consequences

Repository health, metadata, plans, graphs, and quality gates can be viewed visually.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0031 | Provide a Local Repository Dashboard | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0031" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define local dashboard direction"
git push
```

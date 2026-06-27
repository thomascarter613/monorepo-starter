# Step 132 — Record the documentation app decision

**Phase:** `09-workspace-skeleton`

## Purpose

Record that docs will eventually have a dedicated app/site.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0033-provide-a-dedicated-docs-app.md <<'EOF'
# ADR-0033: Provide a Dedicated Docs App

## Status

Accepted

## Date

2026-06-26

## Context

The starter includes extensive documentation that may need a browsable documentation site.

## Decision

Provide `apps/docs` as the documentation site app.

## Consequences

Markdown docs remain source-of-truth while a site can render them later.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0033 | Provide a Dedicated Docs App | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0033" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define docs app direction"
git push
```

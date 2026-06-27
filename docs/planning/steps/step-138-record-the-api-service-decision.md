# Step 138 — Record the API service decision

**Phase:** `09-workspace-skeleton`

## Purpose

Record Elysia as the default API framework direction.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0034-use-elysia-for-the-default-api-service.md <<'EOF'
# ADR-0034: Use Elysia for the Default API Service

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs a Bun-native TypeScript API service path.

## Decision

Use Elysia as the default API framework for the first API service profile.

## Consequences

The default API path aligns with Bun and TypeScript.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0034 | Use Elysia for the Default API Service | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0034" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose elysia for api service"
git push
```

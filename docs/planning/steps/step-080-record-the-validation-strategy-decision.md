# Step 080 — Record the validation strategy decision

**Phase:** `05-shared-packages`

## Purpose

Record ArkType as the default runtime validation layer.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0021-use-arktype-for-runtime-validation.md <<'EOF'
# ADR-0021: Use ArkType for Runtime Validation

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs runtime validation for config, APIs, forms, generated metadata, and CLI inputs.

## Decision

Use ArkType as the default runtime validation library.

## Consequences

Runtime validation stays TypeScript-first and strongly typed.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0021 | Use ArkType for Runtime Validation | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0021" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose arktype for runtime validation"
git push
```

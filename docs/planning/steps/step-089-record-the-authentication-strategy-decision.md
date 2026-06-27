# Step 089 — Record the authentication strategy decision

**Phase:** `05-shared-packages`

## Purpose

Record better-auth as the first default authentication implementation.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0024-use-better-auth-for-default-authentication.md <<'EOF'
# ADR-0024: Use better-auth for Default Authentication

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs provider-agnostic authentication boundaries with a first default implementation.

## Decision

Use better-auth as the first default authentication implementation behind internal auth boundaries.

## Consequences

Auth remains self-hosted and provider-agnostic while giving v1 a practical default.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0024 | Use better-auth for Default Authentication | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0024" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose better-auth for default authentication"
git push
```

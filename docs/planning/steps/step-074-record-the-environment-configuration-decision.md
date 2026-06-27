# Step 074 — Record the environment configuration decision

**Phase:** `04-environments-infra`

## Purpose

Record typed environment validation as a core design decision.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0019-use-typed-environment-configuration.md <<'EOF'
# ADR-0019: Use Typed Environment Configuration

## Status

Accepted

## Date

2026-06-26

## Context

The starter will run across local, test, CI, preview, staging, and production environments.

## Decision

Use typed environment configuration with documented `.env.example` files and runtime validation.

## Consequences

Environment failures become clearer and safer.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0019 | Use Typed Environment Configuration | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0019" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): adopt typed environment configuration"
git push
```

# Step 151 — Record the local services strategy

**Phase:** `10-local-services-observability`

## Purpose

Document which services belong in the local development environment.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0035-include-full-local-service-stack.md <<'EOF'
# ADR-0035: Include a Full Local Service Stack

## Status

Accepted

## Date

2026-06-26

## Context

The starter should demonstrate realistic application infrastructure locally.

## Decision

Include local service profiles for database, cache, object storage, email, events, search, and observability.

## Consequences

Developers can validate realistic flows locally before cloud deployment.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0035 | Include a Full Local Service Stack | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0035" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define local service stack"
git push
```

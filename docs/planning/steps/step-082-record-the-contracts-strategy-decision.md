# Step 082 — Record the contracts strategy decision

**Phase:** `05-shared-packages`

## Purpose

Record OpenAPI-first contracts as the default API contract strategy.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0022-use-openapi-first-contracts.md <<'EOF'
# ADR-0022: Use OpenAPI-First Contracts

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs API contracts that support documentation, validation, and generated clients.

## Decision

Use REST/OpenAPI as the default API contract strategy, while allowing GraphQL and RPC-style profiles later.

## Consequences

API behavior can be documented, tested, and consumed through generated clients.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0022 | Use OpenAPI-First Contracts | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0022" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose openapi-first contracts"
git push
```

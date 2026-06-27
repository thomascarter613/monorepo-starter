# Step 086 — Record the database strategy decision

**Phase:** `05-shared-packages`

## Purpose

Record PostgreSQL and Drizzle as the default database strategy.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0023-use-postgresql-and-drizzle.md <<'EOF'
# ADR-0023: Use PostgreSQL and Drizzle

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs a production-grade relational database and type-safe data access layer.

## Decision

Use PostgreSQL as the default database and Drizzle as the default ORM/query layer.

## Consequences

The data layer is SQL-first, type-safe, and migration-friendly.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0023 | Use PostgreSQL and Drizzle | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0023" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose postgresql and drizzle"
git push
```

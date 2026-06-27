# Step 070 — Record the Docker Compose decision

**Phase:** `04-environments-infra`

## Purpose

Record Docker Compose as the default local-services layer before adding infra files.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0017-use-docker-compose-for-local-services.md <<'EOF'
# ADR-0017: Use Docker Compose for Local Services

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs local databases, queues, object storage, search, email, and observability services.

## Decision

Use Docker Compose as the default local service orchestration layer.

## Consequences

Developers can run local infrastructure without Kubernetes.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0017 | Use Docker Compose for Local Services | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0017" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose docker compose for local services"
git push
```

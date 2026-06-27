# Step 076 — Record the logging strategy decision

**Phase:** `05-shared-packages`

## Purpose

Record the decision to use pino as the default structured logger.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0020-use-pino-for-structured-logging.md <<'EOF'
# ADR-0020: Use pino for Structured Logging

## Status

Accepted

## Date

2026-06-26

## Context

Applications, services, workers, and CLI tools need consistent structured logging.

## Decision

Use pino as the default logging library.

## Consequences

Logs are fast, structured, and compatible with future observability pipelines.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0020 | Use pino for Structured Logging | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0020" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose pino for structured logging"
git push
```

# Step 097 — Record the telemetry strategy decision

**Phase:** `05-shared-packages`

## Purpose

Record OpenTelemetry as the default instrumentation standard.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0026-use-opentelemetry-for-instrumentation.md <<'EOF'
# ADR-0026: Use OpenTelemetry for Instrumentation

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs vendor-neutral observability across apps, services, jobs, and CLI operations.

## Decision

Use OpenTelemetry as the default instrumentation standard.

## Consequences

Traces, metrics, and logs can be routed to local and hosted observability stacks.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0026 | Use OpenTelemetry for Instrumentation | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0026" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose opentelemetry for instrumentation"
git push
```

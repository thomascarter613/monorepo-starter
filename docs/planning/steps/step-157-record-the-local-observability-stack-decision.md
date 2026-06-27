# Step 157 — Record the local observability stack decision

**Phase:** `10-local-services-observability`

## Purpose

Record OpenTelemetry plus Grafana stack as the local observability direction.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0036-use-grafana-stack-for-local-observability.md <<'EOF'
# ADR-0036: Use Grafana Stack for Local Observability

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs local visibility into logs, metrics, and traces.

## Decision

Use OpenTelemetry Collector, Grafana, Prometheus, Loki, and Tempo as the local observability stack.

## Consequences

Developers can inspect telemetry locally and adapt to hosted providers later.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0036 | Use Grafana Stack for Local Observability | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0036" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define local observability stack"
git push
```

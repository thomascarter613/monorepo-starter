# Step 158 — Add observability configuration placeholders

**Phase:** `10-local-services-observability`

## Purpose

Create config folders for local observability services.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p infra/observability/otel infra/observability/prometheus infra/observability/grafana

cat > infra/observability/README.md <<'EOF'
# Observability

Local observability uses OpenTelemetry Collector, Grafana, Prometheus, Loki, and Tempo.
EOF

cat > infra/observability/prometheus/prometheus.yml <<'EOF'
global:
  scrape_interval: 15s
scrape_configs:
  - job_name: prometheus
    static_configs:
      - targets: ["localhost:9090"]
EOF
```

## Validate

```bash
test -f infra/observability/prometheus/prometheus.yml
```

## Commit

```bash
git add .
git commit -m "chore(observability): add config placeholders"
git push
```

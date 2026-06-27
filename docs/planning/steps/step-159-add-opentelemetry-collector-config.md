# Step 159 — Add OpenTelemetry Collector config

**Phase:** `10-local-services-observability`

## Purpose

Create a basic local OTel collector configuration.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > infra/observability/otel/collector.yaml <<'EOF'
receivers:
  otlp:
    protocols:
      grpc:
      http:

exporters:
  logging:
    verbosity: basic

service:
  pipelines:
    traces:
      receivers: [otlp]
      exporters: [logging]
    metrics:
      receivers: [otlp]
      exporters: [logging]
    logs:
      receivers: [otlp]
      exporters: [logging]
EOF
```

## Validate

```bash
test -f infra/observability/otel/collector.yaml
```

## Commit

```bash
git add .
git commit -m "chore(observability): add otel collector config"
git push
```

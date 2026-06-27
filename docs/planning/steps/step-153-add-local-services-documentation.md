# Step 153 — Add local services documentation

**Phase:** `10-local-services-observability`

## Purpose

Document how to start, stop, and inspect local services.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p docs/operations

cat > docs/operations/local-services.md <<'EOF'
# Local Services

Start local services:

```bash
bun run services:up
```

View logs:

```bash
bun run services:logs
```

Stop local services:

```bash
bun run services:down
```

Included baseline services:

- PostgreSQL
- Valkey
- MinIO
- Mailpit
- NATS
- Meilisearch
EOF
```

## Validate

```bash
test -f docs/operations/local-services.md
```

## Commit

```bash
git add .
git commit -m "docs(operations): add local services guide"
git push
```

# Step 152 — Add NATS and Meilisearch to Docker Compose

**Phase:** `10-local-services-observability`

## Purpose

Extend local services with an event bus and search engine.

## Commands

Run from the repository root unless stated otherwise.

```bash
python - <<'PY'
from pathlib import Path
p=Path('infra/docker/compose.yaml')
text=p.read_text()
if 'nats:' not in text:
  text=text.replace('volumes:\n  postgres-data:\n  minio-data:\n', """  nats:
    image: nats:2-alpine
    command: ["-js"]
    ports:
      - "4222:4222"
      - "8222:8222"

  meilisearch:
    image: getmeili/meilisearch:v1.10
    environment:
      MEILI_NO_ANALYTICS: "true"
      MEILI_MASTER_KEY: local-master-key
    ports:
      - "7700:7700"
    volumes:
      - meilisearch-data:/meili_data

volumes:
  postgres-data:
  minio-data:
  meilisearch-data:
""")
p.write_text(text)
PY
```

## Validate

```bash
docker compose -f infra/docker/compose.yaml config >/dev/null
```

## Commit

```bash
git add .
git commit -m "chore(infra): add nats and meilisearch services"
git push
```

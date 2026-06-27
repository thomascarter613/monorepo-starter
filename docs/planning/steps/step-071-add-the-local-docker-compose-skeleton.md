# Step 071 — Add the local Docker Compose skeleton

**Phase:** `04-environments-infra`

## Purpose

Create the first local infrastructure compose file.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p infra/docker

cat > infra/docker/compose.yaml <<'EOF'
services:
  postgres:
    image: postgres:17-alpine
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: monorepo_starter
    ports:
      - "5432:5432"
    volumes:
      - postgres-data:/var/lib/postgresql/data

  valkey:
    image: valkey/valkey:8-alpine
    ports:
      - "6379:6379"

  minio:
    image: minio/minio:latest
    command: server /data --console-address ":9001"
    environment:
      MINIO_ROOT_USER: minio
      MINIO_ROOT_PASSWORD: minio123
    ports:
      - "9000:9000"
      - "9001:9001"
    volumes:
      - minio-data:/data

  mailpit:
    image: axllent/mailpit:latest
    ports:
      - "1025:1025"
      - "8025:8025"

volumes:
  postgres-data:
  minio-data:
EOF

bun pm pkg set scripts.services:up="docker compose -f infra/docker/compose.yaml up -d"
bun pm pkg set scripts.services:down="docker compose -f infra/docker/compose.yaml down"
bun pm pkg set scripts.services:logs="docker compose -f infra/docker/compose.yaml logs -f"
```

## Validate

```bash
docker compose -f infra/docker/compose.yaml config >/dev/null
```

## Commit

```bash
git add .
git commit -m "chore(infra): add local docker compose skeleton"
git push
```

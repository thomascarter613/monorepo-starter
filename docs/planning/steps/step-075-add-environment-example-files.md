# Step 075 — Add environment example files

**Phase:** `04-environments-infra`

## Purpose

Create safe local environment examples.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > .env.example <<'EOF'
NODE_ENV=development
APP_ENV=local
DATABASE_URL=postgres://postgres:postgres@localhost:5432/monorepo_starter
REDIS_URL=redis://localhost:6379
S3_ENDPOINT=http://localhost:9000
S3_ACCESS_KEY_ID=minio
S3_SECRET_ACCESS_KEY=minio123
S3_BUCKET=monorepo-starter-local
SMTP_HOST=localhost
SMTP_PORT=1025
EOF

mkdir -p docs/reference

cat > docs/reference/environment.md <<'EOF'
# Environment Variables

Copy `.env.example` to `.env` for local development.

```bash
cp .env.example .env
```

Never commit `.env` files.
EOF
```

## Validate

```bash
test -f .env.example && test -f docs/reference/environment.md
```

## Commit

```bash
git add .
git commit -m "chore(env): add environment examples"
git push
```

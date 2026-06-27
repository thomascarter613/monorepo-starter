# Step 154 — Add database migration script placeholders

**Phase:** `10-local-services-observability`

## Purpose

Add root scripts for future database migration workflows.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun pm pkg set scripts.db:generate="cd packages/db && drizzle-kit generate"
bun pm pkg set scripts.db:migrate="cd packages/db && drizzle-kit migrate"
bun pm pkg set scripts.db:studio="cd packages/db && drizzle-kit studio"
```

## Validate

```bash
bun pm pkg get scripts.db:generate
```

## Commit

```bash
git add .
git commit -m "chore(db): add migration scripts"
git push
```

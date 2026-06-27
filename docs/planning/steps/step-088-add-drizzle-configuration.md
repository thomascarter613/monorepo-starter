# Step 088 — Add Drizzle configuration

**Phase:** `05-shared-packages`

## Purpose

Create the first Drizzle config and migrations folder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/db/drizzle packages/db/src/schema

cat > packages/db/drizzle.config.ts <<'EOF'
import { defineConfig } from "drizzle-kit";

export default defineConfig({
  schema: "./src/schema/index.ts",
  out: "./drizzle",
  dialect: "postgresql",
  dbCredentials: {
    url: process.env.DATABASE_URL ?? "postgres://postgres:postgres@localhost:5432/monorepo_starter"
  }
});
EOF

cat > packages/db/src/schema/index.ts <<'EOF'
export {};
EOF
```

## Validate

```bash
test -f packages/db/drizzle.config.ts
```

## Commit

```bash
git add .
git commit -m "chore(db): add drizzle configuration"
git push
```

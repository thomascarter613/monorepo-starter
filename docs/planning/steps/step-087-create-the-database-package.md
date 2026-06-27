# Step 087 — Create the database package

**Phase:** `05-shared-packages`

## Purpose

Add the database package with Drizzle placeholders.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add drizzle-orm postgres
bun add -d drizzle-kit
mkdir -p packages/db/src

cat > packages/db/package.json <<'EOF'
{
  "name": "@monorepo-starter/db",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "main": "./src/index.ts",
  "types": "./src/index.ts",
  "exports": { ".": "./src/index.ts" },
  "dependencies": { "drizzle-orm": "latest", "postgres": "latest" },
  "scripts": { "typecheck": "tsc -p tsconfig.json --pretty false" }
}
EOF

cat > packages/db/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > packages/db/src/index.ts <<'EOF'
export const dbPackageName = "@monorepo-starter/db";
EOF
```

## Validate

```bash
cd packages/db && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "feat(db): add database package skeleton"
git push
```

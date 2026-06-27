# Step 135 — Create apps/admin skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Internal administration console placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p apps/admin/src

cat > apps/admin/package.json <<'EOF'
{
  "name": "@monorepo-starter/admin",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for apps/admin yet'",
    "dev": "echo 'dev server not implemented for apps/admin yet'"
  }
}
EOF

cat > apps/admin/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts", "src/**/*.tsx"] }
EOF

cat > apps/admin/src/index.ts <<'EOF'
export const appName = "@monorepo-starter/admin";
EOF

cat > apps/admin/README.md <<'EOF'
# apps/admin

Internal administration console placeholder.
EOF
```

## Validate

```bash
cd apps/admin && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(apps): add admin skeleton"
git push
```

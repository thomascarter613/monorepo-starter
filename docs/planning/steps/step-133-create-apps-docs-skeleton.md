# Step 133 — Create apps/docs skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Dedicated documentation site placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p apps/docs/src

cat > apps/docs/package.json <<'EOF'
{
  "name": "@monorepo-starter/docs",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for apps/docs yet'",
    "dev": "echo 'dev server not implemented for apps/docs yet'"
  }
}
EOF

cat > apps/docs/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts", "src/**/*.tsx"] }
EOF

cat > apps/docs/src/index.ts <<'EOF'
export const appName = "@monorepo-starter/docs";
EOF

cat > apps/docs/README.md <<'EOF'
# apps/docs

Dedicated documentation site placeholder.
EOF
```

## Validate

```bash
cd apps/docs && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(apps): add docs skeleton"
git push
```

# Step 134 — Create apps/web skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Primary public and authenticated web application placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p apps/web/src

cat > apps/web/package.json <<'EOF'
{
  "name": "@monorepo-starter/web",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for apps/web yet'",
    "dev": "echo 'dev server not implemented for apps/web yet'"
  }
}
EOF

cat > apps/web/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts", "src/**/*.tsx"] }
EOF

cat > apps/web/src/index.ts <<'EOF'
export const appName = "@monorepo-starter/web";
EOF

cat > apps/web/README.md <<'EOF'
# apps/web

Primary public and authenticated web application placeholder.
EOF
```

## Validate

```bash
cd apps/web && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(apps): add web skeleton"
git push
```

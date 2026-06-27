# Step 137 — Create apps/playground skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Safe sandbox for examples, experiments, and generated demos.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p apps/playground/src

cat > apps/playground/package.json <<'EOF'
{
  "name": "@monorepo-starter/playground",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for apps/playground yet'",
    "dev": "echo 'dev server not implemented for apps/playground yet'"
  }
}
EOF

cat > apps/playground/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts", "src/**/*.tsx"] }
EOF

cat > apps/playground/src/index.ts <<'EOF'
export const appName = "@monorepo-starter/playground";
EOF

cat > apps/playground/README.md <<'EOF'
# apps/playground

Safe sandbox for examples, experiments, and generated demos.
EOF
```

## Validate

```bash
cd apps/playground && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(apps): add playground skeleton"
git push
```

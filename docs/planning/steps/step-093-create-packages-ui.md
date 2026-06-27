# Step 093 — Create packages/ui

**Phase:** `05-shared-packages`

## Purpose

Shared UI primitives, design tokens, and component conventions.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/ui/src

cat > packages/ui/package.json <<'EOF'
{
  "name": "@monorepo-starter/ui",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "main": "./src/index.ts",
  "types": "./src/index.ts",
  "exports": {
    ".": "./src/index.ts"
  },
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run"
  }
}
EOF

cat > packages/ui/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/ui/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/ui";
export const uiPackageName = "@monorepo-starter/ui";
EOF

cat > packages/ui/README.md <<'EOF'
# @monorepo-starter/ui

Shared UI primitives, design tokens, and component conventions.
EOF
```

## Validate

```bash
cd packages/ui && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add ui package"
git push
```

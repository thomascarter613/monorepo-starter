# Step 094 — Create packages/tsconfig

**Phase:** `05-shared-packages`

## Purpose

Shared TypeScript configuration package.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/tsconfig/src

cat > packages/tsconfig/package.json <<'EOF'
{
  "name": "@monorepo-starter/tsconfig",
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

cat > packages/tsconfig/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/tsconfig/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/tsconfig";
export const tsconfigPackageName = "@monorepo-starter/tsconfig";
EOF

cat > packages/tsconfig/README.md <<'EOF'
# @monorepo-starter/tsconfig

Shared TypeScript configuration package.
EOF
```

## Validate

```bash
cd packages/tsconfig && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add tsconfig package"
git push
```

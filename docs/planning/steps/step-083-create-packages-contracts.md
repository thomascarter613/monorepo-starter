# Step 083 — Create packages/contracts

**Phase:** `05-shared-packages`

## Purpose

Shared API, event, schema, DTO, and validation contracts.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/contracts/src

cat > packages/contracts/package.json <<'EOF'
{
  "name": "@monorepo-starter/contracts",
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

cat > packages/contracts/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/contracts/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/contracts";
export const contractVersion = "0.0.0";
EOF

cat > packages/contracts/README.md <<'EOF'
# @monorepo-starter/contracts

Shared API, event, schema, DTO, and validation contracts.
EOF
```

## Validate

```bash
cd packages/contracts && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add contracts package"
git push
```

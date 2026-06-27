# Step 081 — Create the validation package

**Phase:** `05-shared-packages`

## Purpose

Add the shared validation package with ArkType.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add arktype
mkdir -p packages/validation/src

cat > packages/validation/package.json <<'EOF'
{
  "name": "@monorepo-starter/validation",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "main": "./src/index.ts",
  "types": "./src/index.ts",
  "exports": { ".": "./src/index.ts" },
  "dependencies": { "arktype": "latest" },
  "scripts": { "typecheck": "tsc -p tsconfig.json --pretty false" }
}
EOF

cat > packages/validation/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > packages/validation/src/index.ts <<'EOF'
export { type } from "arktype";
EOF
```

## Validate

```bash
cd packages/validation && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "feat(validation): add arktype validation package"
git push
```

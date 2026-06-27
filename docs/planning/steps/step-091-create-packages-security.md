# Step 091 — Create packages/security

**Phase:** `05-shared-packages`

## Purpose

Shared security helpers, policy utilities, and safe defaults.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/security/src

cat > packages/security/package.json <<'EOF'
{
  "name": "@monorepo-starter/security",
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

cat > packages/security/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/security/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/security";
export const securityPackageName = "@monorepo-starter/security";
EOF

cat > packages/security/README.md <<'EOF'
# @monorepo-starter/security

Shared security helpers, policy utilities, and safe defaults.
EOF
```

## Validate

```bash
cd packages/security && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add security package"
git push
```

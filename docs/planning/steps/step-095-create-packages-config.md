# Step 095 — Create packages/config

**Phase:** `05-shared-packages`

## Purpose

Shared tool and application configuration package.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/config/src

cat > packages/config/package.json <<'EOF'
{
  "name": "@monorepo-starter/config",
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

cat > packages/config/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/config/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/config";
export const configPackageName = "@monorepo-starter/config";
EOF

cat > packages/config/README.md <<'EOF'
# @monorepo-starter/config

Shared tool and application configuration package.
EOF
```

## Validate

```bash
cd packages/config && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add config package"
git push
```

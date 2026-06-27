# Step 084 — Create packages/api-client

**Phase:** `05-shared-packages`

## Purpose

Type-safe API client package for generated or hand-written clients.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/api-client/src

cat > packages/api-client/package.json <<'EOF'
{
  "name": "@monorepo-starter/api-client",
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

cat > packages/api-client/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/api-client/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/api-client";
export function createApiClient(baseUrl: string) { return { baseUrl }; }
EOF

cat > packages/api-client/README.md <<'EOF'
# @monorepo-starter/api-client

Type-safe API client package for generated or hand-written clients.
EOF
```

## Validate

```bash
cd packages/api-client && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add api-client package"
git push
```

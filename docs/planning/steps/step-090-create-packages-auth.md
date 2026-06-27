# Step 090 — Create packages/auth

**Phase:** `05-shared-packages`

## Purpose

Shared authentication, session, roles, and permission helpers.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/auth/src

cat > packages/auth/package.json <<'EOF'
{
  "name": "@monorepo-starter/auth",
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

cat > packages/auth/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/auth/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/auth";
export type Role = "admin" | "member" | "viewer";
EOF

cat > packages/auth/README.md <<'EOF'
# @monorepo-starter/auth

Shared authentication, session, roles, and permission helpers.
EOF
```

## Validate

```bash
cd packages/auth && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add auth package"
git push
```

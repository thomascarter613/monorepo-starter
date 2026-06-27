# Step 078 — Create packages/errors

**Phase:** `05-shared-packages`

## Purpose

Shared error types and result helpers.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/errors/src

cat > packages/errors/package.json <<'EOF'
{
  "name": "@monorepo-starter/errors",
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

cat > packages/errors/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/errors/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/errors";
export type Result<T, E = Error> = { ok: true; value: T } | { ok: false; error: E };
EOF

cat > packages/errors/README.md <<'EOF'
# @monorepo-starter/errors

Shared error types and result helpers.
EOF
```

## Validate

```bash
cd packages/errors && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add errors package"
git push
```

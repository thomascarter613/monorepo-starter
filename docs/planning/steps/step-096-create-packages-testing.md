# Step 096 — Create packages/testing

**Phase:** `05-shared-packages`

## Purpose

Shared test utilities, fixtures, and testing helpers.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/testing/src

cat > packages/testing/package.json <<'EOF'
{
  "name": "@monorepo-starter/testing",
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

cat > packages/testing/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/testing/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/testing";
export function createTestName(name: string) { return `test:${name}`; }
EOF

cat > packages/testing/README.md <<'EOF'
# @monorepo-starter/testing

Shared test utilities, fixtures, and testing helpers.
EOF
```

## Validate

```bash
cd packages/testing && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add testing package"
git push
```

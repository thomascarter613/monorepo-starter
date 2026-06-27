# Step 079 — Create packages/env

**Phase:** `05-shared-packages`

## Purpose

Typed environment loading and validation helpers.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/env/src

cat > packages/env/package.json <<'EOF'
{
  "name": "@monorepo-starter/env",
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

cat > packages/env/tsconfig.json <<'EOF'
{
  "extends": "../../tsconfig.base.json",
  "compilerOptions": {
    "rootDir": "src"
  },
  "include": ["src/**/*.ts"]
}
EOF

cat > packages/env/src/index.ts <<'EOF'
export const packageName = "@monorepo-starter/env";
export function getEnv(name: string): string | undefined { return process.env[name]; }
EOF

cat > packages/env/README.md <<'EOF'
# @monorepo-starter/env

Typed environment loading and validation helpers.
EOF
```

## Validate

```bash
cd packages/env && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(packages): add env package"
git push
```

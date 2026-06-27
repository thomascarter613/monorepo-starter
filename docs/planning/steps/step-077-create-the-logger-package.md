# Step 077 — Create the logger package

**Phase:** `05-shared-packages`

## Purpose

Add the shared logger package.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add pino
mkdir -p packages/logger/src

cat > packages/logger/package.json <<'EOF'
{
  "name": "@monorepo-starter/logger",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "main": "./src/index.ts",
  "types": "./src/index.ts",
  "exports": { ".": "./src/index.ts" },
  "dependencies": { "pino": "latest" },
  "scripts": { "typecheck": "tsc -p tsconfig.json --pretty false" }
}
EOF

cat > packages/logger/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > packages/logger/src/index.ts <<'EOF'
import pino from "pino";

export function createLogger(name: string) {
  return pino({ name });
}
EOF
```

## Validate

```bash
cd packages/logger && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "feat(logger): add shared logger package"
git push
```

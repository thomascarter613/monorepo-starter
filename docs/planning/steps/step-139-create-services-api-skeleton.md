# Step 139 — Create services/api skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Main API service placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p services/api/src

cat > services/api/package.json <<'EOF'
{
  "name": "@monorepo-starter/service-api",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for services/api yet'",
    "dev": "bun src/index.ts"
  }
}
EOF

cat > services/api/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > services/api/src/index.ts <<'EOF'
console.log("services/api placeholder");
EOF

cat > services/api/README.md <<'EOF'
# services/api

Main API service placeholder.
EOF
```

## Validate

```bash
cd services/api && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(services): add api skeleton"
git push
```

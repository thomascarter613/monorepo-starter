# Step 140 — Create services/worker skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Background job worker placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p services/worker/src

cat > services/worker/package.json <<'EOF'
{
  "name": "@monorepo-starter/service-worker",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for services/worker yet'",
    "dev": "bun src/index.ts"
  }
}
EOF

cat > services/worker/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > services/worker/src/index.ts <<'EOF'
console.log("services/worker placeholder");
EOF

cat > services/worker/README.md <<'EOF'
# services/worker

Background job worker placeholder.
EOF
```

## Validate

```bash
cd services/worker && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(services): add worker skeleton"
git push
```

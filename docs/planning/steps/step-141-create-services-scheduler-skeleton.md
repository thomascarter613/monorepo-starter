# Step 141 — Create services/scheduler skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Scheduled tasks and recurring workflow placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p services/scheduler/src

cat > services/scheduler/package.json <<'EOF'
{
  "name": "@monorepo-starter/service-scheduler",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for services/scheduler yet'",
    "dev": "bun src/index.ts"
  }
}
EOF

cat > services/scheduler/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > services/scheduler/src/index.ts <<'EOF'
console.log("services/scheduler placeholder");
EOF

cat > services/scheduler/README.md <<'EOF'
# services/scheduler

Scheduled tasks and recurring workflow placeholder.
EOF
```

## Validate

```bash
cd services/scheduler && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(services): add scheduler skeleton"
git push
```

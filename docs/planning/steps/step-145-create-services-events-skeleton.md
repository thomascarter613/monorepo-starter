# Step 145 — Create services/events skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Domain and integration events service placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p services/events/src

cat > services/events/package.json <<'EOF'
{
  "name": "@monorepo-starter/service-events",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for services/events yet'",
    "dev": "bun src/index.ts"
  }
}
EOF

cat > services/events/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > services/events/src/index.ts <<'EOF'
console.log("services/events placeholder");
EOF

cat > services/events/README.md <<'EOF'
# services/events

Domain and integration events service placeholder.
EOF
```

## Validate

```bash
cd services/events && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(services): add events skeleton"
git push
```

# Step 144 — Create services/search skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Search indexing and query service placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p services/search/src

cat > services/search/package.json <<'EOF'
{
  "name": "@monorepo-starter/service-search",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for services/search yet'",
    "dev": "bun src/index.ts"
  }
}
EOF

cat > services/search/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > services/search/src/index.ts <<'EOF'
console.log("services/search placeholder");
EOF

cat > services/search/README.md <<'EOF'
# services/search

Search indexing and query service placeholder.
EOF
```

## Validate

```bash
cd services/search && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(services): add search skeleton"
git push
```

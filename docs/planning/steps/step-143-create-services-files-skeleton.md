# Step 143 — Create services/files skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

File upload, object storage, and media metadata placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p services/files/src

cat > services/files/package.json <<'EOF'
{
  "name": "@monorepo-starter/service-files",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for services/files yet'",
    "dev": "bun src/index.ts"
  }
}
EOF

cat > services/files/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > services/files/src/index.ts <<'EOF'
console.log("services/files placeholder");
EOF

cat > services/files/README.md <<'EOF'
# services/files

File upload, object storage, and media metadata placeholder.
EOF
```

## Validate

```bash
cd services/files && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(services): add files skeleton"
git push
```

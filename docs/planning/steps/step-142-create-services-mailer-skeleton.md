# Step 142 — Create services/mailer skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Email sending and notification delivery placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p services/mailer/src

cat > services/mailer/package.json <<'EOF'
{
  "name": "@monorepo-starter/service-mailer",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for services/mailer yet'",
    "dev": "bun src/index.ts"
  }
}
EOF

cat > services/mailer/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > services/mailer/src/index.ts <<'EOF'
console.log("services/mailer placeholder");
EOF

cat > services/mailer/README.md <<'EOF'
# services/mailer

Email sending and notification delivery placeholder.
EOF
```

## Validate

```bash
cd services/mailer && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(services): add mailer skeleton"
git push
```

# Step 111 — Create the moro package skeleton

**Phase:** `07-moro-cli`

## Purpose

Add the initial package for the `moro` CLI.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p packages/moro/src

cat > packages/moro/package.json <<'EOF'
{
  "name": "@monorepo-starter/moro",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "bin": {
    "moro": "./src/index.ts"
  },
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run"
  }
}
EOF

cat > packages/moro/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts"] }
EOF

cat > packages/moro/README.md <<'EOF'
# moro

`moro` is the CLI for `monorepo-starter`.
EOF
```

## Validate

```bash
test -f packages/moro/package.json
```

## Commit

```bash
git add .
git commit -m "feat(cli): add moro package skeleton"
git push
```

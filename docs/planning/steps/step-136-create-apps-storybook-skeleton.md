# Step 136 — Create apps/storybook skeleton

**Phase:** `09-workspace-skeleton`

## Purpose

Component documentation and visual testing placeholder.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p apps/storybook/src

cat > apps/storybook/package.json <<'EOF'
{
  "name": "@monorepo-starter/storybook",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "scripts": {
    "typecheck": "tsc -p tsconfig.json --pretty false",
    "test": "vitest run",
    "build": "echo 'build not implemented for apps/storybook yet'",
    "dev": "echo 'dev server not implemented for apps/storybook yet'"
  }
}
EOF

cat > apps/storybook/tsconfig.json <<'EOF'
{ "extends": "../../tsconfig.base.json", "include": ["src/**/*.ts", "src/**/*.tsx"] }
EOF

cat > apps/storybook/src/index.ts <<'EOF'
export const appName = "@monorepo-starter/storybook";
EOF

cat > apps/storybook/README.md <<'EOF'
# apps/storybook

Component documentation and visual testing placeholder.
EOF
```

## Validate

```bash
cd apps/storybook && bun run typecheck
```

## Commit

```bash
git add .
git commit -m "chore(apps): add storybook skeleton"
git push
```

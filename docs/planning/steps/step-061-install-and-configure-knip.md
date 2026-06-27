# Step 061 — Install and configure Knip

**Phase:** `03-tooling-foundation`

## Purpose

Add dead-code and unused-dependency detection.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d knip

cat > knip.json <<'EOF'
{
  "$schema": "https://unpkg.com/knip@5/schema.json",
  "entry": ["scripts/**/*.sh"],
  "project": ["**/*.{js,jsx,ts,tsx,mjs,cjs,json}"],
  "ignore": ["node_modules/**", "dist/**", "build/**", "coverage/**"],
  "ignoreDependencies": ["@moonrepo/cli"]
}
EOF

bun pm pkg set scripts.deadcode="knip"
```

## Validate

```bash
bun run deadcode || true
```

## Commit

```bash
git add .
git commit -m "chore(repo): add knip dead-code detection"
git push
```

## Notes

The first Knip run may need tuning as packages are added. Keep fixes intentional.

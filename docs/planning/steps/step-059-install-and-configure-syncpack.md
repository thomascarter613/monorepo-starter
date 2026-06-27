# Step 059 — Install and configure Syncpack

**Phase:** `03-tooling-foundation`

## Purpose

Add dependency consistency checks.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d syncpack

cat > .syncpackrc.json <<'EOF'
{
  "versionGroups": [
    {
      "label": "Use exact versions by default",
      "dependencies": ["**"],
      "dependencyTypes": ["dev", "prod", "peer"],
      "pinVersion": true
    }
  ],
  "semverGroups": [
    {
      "label": "Disallow loose ranges",
      "range": "",
      "dependencies": ["**"]
    }
  ]
}
EOF

bun pm pkg set scripts.deps:check="syncpack lint && syncpack format --check"
bun pm pkg set scripts.deps:fix="syncpack fix-mismatches && syncpack format"
```

## Validate

```bash
bun run deps:check
```

## Commit

```bash
git add .
git commit -m "chore(deps): add syncpack"
git push
```

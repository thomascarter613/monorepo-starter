# Step 047 — Install and configure commitlint

**Phase:** `03-tooling-foundation`

## Purpose

Add commit message validation for Conventional Commits.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d @commitlint/cli @commitlint/config-conventional

cat > commitlint.config.cjs <<'EOF'
module.exports = {
  extends: ["@commitlint/config-conventional"],
  rules: {
    "body-max-line-length": [0],
    "footer-max-line-length": [0]
  }
};
EOF

bun pm pkg set scripts.commitlint="commitlint --edit"
```

## Validate

```bash
echo "chore(repo): test commitlint" | bunx commitlint
```

## Commit

```bash
git add .
git commit -m "chore(commits): add commitlint"
git push
```

# Step 173 — Add security CI workflow skeleton

**Phase:** `12-release-ci`

## Purpose

Add a first security workflow with secret scanning placeholders.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > .github/workflows/security.yml <<'EOF'
name: Security

on:
  pull_request:
  push:
    branches: [main]
  schedule:
    - cron: "0 8 * * 1"

permissions:
  contents: read
  security-events: write

jobs:
  gitleaks:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 0

      - name: Run Gitleaks
        uses: gitleaks/gitleaks-action@v2
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
EOF
```

## Validate

```bash
test -f .github/workflows/security.yml
```

## Commit

```bash
git add .
git commit -m "ci(security): add security workflow skeleton"
git push
```

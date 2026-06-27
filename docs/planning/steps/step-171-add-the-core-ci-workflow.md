# Step 171 — Add the core CI workflow

**Phase:** `12-release-ci`

## Purpose

Add the first GitHub Actions workflow for install and validation.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p .github/workflows

cat > .github/workflows/ci.yml <<'EOF'
name: CI

on:
  pull_request:
  push:
    branches: [main]

permissions:
  contents: read

jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Bun
        uses: oven-sh/setup-bun@v2

      - name: Install dependencies
        run: bun install --frozen-lockfile

      - name: Run checks
        run: bun run check
EOF
```

## Validate

```bash
test -f .github/workflows/ci.yml
```

## Commit

```bash
git add .
git commit -m "ci(github): add core ci workflow"
git push
```

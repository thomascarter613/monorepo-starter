# Step 172 — Add documentation CI workflow

**Phase:** `12-release-ci`

## Purpose

Add a separate workflow for documentation checks.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > .github/workflows/docs.yml <<'EOF'
name: Docs

on:
  pull_request:
  push:
    branches: [main]

permissions:
  contents: read

jobs:
  markdown:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Bun
        uses: oven-sh/setup-bun@v2

      - name: Install dependencies
        run: bun install --frozen-lockfile

      - name: Lint Markdown
        run: bun run lint:md
EOF
```

## Validate

```bash
test -f .github/workflows/docs.yml
```

## Commit

```bash
git add .
git commit -m "ci(github): add docs workflow"
git push
```

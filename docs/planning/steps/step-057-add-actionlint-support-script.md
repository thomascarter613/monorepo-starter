# Step 057 — Add actionlint support script

**Phase:** `03-tooling-foundation`

## Purpose

Prepare GitHub Actions linting before workflows are introduced.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun pm pkg set scripts.lint:actions="actionlint"

cat > docs/development/actionlint.md <<'EOF'
# actionlint

GitHub Actions workflows should be linted with `actionlint`.

## Validate

```bash
bun run lint:actions
```

Install `actionlint` through your OS package manager, mise, or the official release binary.
EOF
```

## Validate

```bash
test -f docs/development/actionlint.md
```

## Commit

```bash
git add .
git commit -m "chore(ci): add actionlint script and docs"
git push
```

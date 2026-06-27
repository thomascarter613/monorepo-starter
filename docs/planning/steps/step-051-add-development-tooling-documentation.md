# Step 051 — Add development tooling documentation

**Phase:** `03-tooling-foundation`

## Purpose

Document the first local tooling layer: Biome, moon, commitlint, and Lefthook.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/development/tooling.md <<'EOF'
# Tooling

## Runtime and Package Manager

Bun is the default runtime and package manager.

## Task Runner

moon orchestrates monorepo tasks.

## Formatter and Linter

Biome formats and lints TypeScript, JavaScript, JSON, and supported files.

## Commit Validation

commitlint validates Conventional Commit messages.

## Git Hooks

Lefthook runs local Git hooks.

## Baseline Command

```bash
bun run check
```
EOF
```

## Validate

```bash
test -f docs/development/tooling.md
```

## Commit

```bash
git add .
git commit -m "docs(development): document tooling baseline"
git push
```

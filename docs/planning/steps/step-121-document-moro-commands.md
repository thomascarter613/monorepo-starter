# Step 121 — Document moro commands

**Phase:** `07-moro-cli`

## Purpose

Create the first CLI command reference.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p docs/cli

cat > docs/cli/commands.md <<'EOF'
# moro Commands

## Help

```bash
bun run moro --help
```

## Doctor

```bash
bun run moro doctor
```

## Check

```bash
bun run moro check
```

## Plan

```bash
bun run moro plan
```

## Init

```bash
bun run moro init my-project --profile fullstack-app
```
EOF
```

## Validate

```bash
test -f docs/cli/commands.md
```

## Commit

```bash
git add .
git commit -m "docs(cli): add command reference"
git push
```

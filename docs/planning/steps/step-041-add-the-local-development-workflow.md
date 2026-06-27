# Step 041 — Add the local development workflow

**Phase:** `02-documentation-foundation`

## Purpose

Document the standard local workflow before more tools are introduced.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p docs/development

cat > docs/development/workflow.md <<'EOF'
# Development Workflow

## Setup

```bash
bun install
```

## Validate

```bash
bun run check
```

## Format

```bash
bun run format
```

## Typecheck

```bash
bun run typecheck
```

## Commit

Use Conventional Commits.

```bash
git add .
git commit -m "type(scope): summary"
```

## Rule

Add an ADR before introducing major tools, architectural structure, or workflow conventions.
EOF
```

## Validate

```bash
test -f docs/development/workflow.md
```

## Commit

```bash
git add .
git commit -m "docs(development): add local workflow"
git push
```

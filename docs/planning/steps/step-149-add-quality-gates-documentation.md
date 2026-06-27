# Step 149 — Add quality gates documentation

**Phase:** `09-workspace-skeleton`

## Purpose

Document required validation gates before CI is introduced.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/governance/quality-gates.md <<'EOF'
# Quality Gates

The default validation command is:

```bash
bun run check
```

## Required Gate Families

- formatting
- linting
- typechecking
- unit tests
- e2e tests where applicable
- dependency consistency
- dead-code detection
- architecture checks
- security checks
- documentation checks
- release validation

## Rule

No merge or release should happen unless required gates pass or a documented exception is approved.
EOF
```

## Validate

```bash
test -f docs/governance/quality-gates.md
```

## Commit

```bash
git add .
git commit -m "docs(governance): add quality gates"
git push
```

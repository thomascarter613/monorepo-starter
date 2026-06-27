# Step 123 — Document template variables

**Phase:** `07-moro-cli`

## Purpose

Create the first template variable reference.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/cli/templates.md <<'EOF'
# Templates

Templates may use variables supplied by `moro`.

## Initial Variables

- `projectName`
- `packageManager`
- `profile`
- `appName`
- `packageName`
- `serviceName`
- `year`

## Rule

Template variables should be documented when introduced.
EOF
```

## Validate

```bash
test -f docs/cli/templates.md
```

## Commit

```bash
git add .
git commit -m "docs(cli): document template variables"
git push
```

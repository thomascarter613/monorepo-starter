# Step 108 — Add templates documentation

**Phase:** `06-architecture-governance`

## Purpose

Create the starting documentation for generator templates.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > templates/README.md <<'EOF'
# Templates

This directory contains templates used by the future `moro` CLI.

## Template Rules

- Templates should be small and composable.
- Generated files should include clear ownership metadata where practical.
- Risky overwrites must require dry-run and confirmation behavior.
- Templates should be documented beside their profile or generator.
EOF
```

## Validate

```bash
test -f templates/README.md
```

## Commit

```bash
git add .
git commit -m "docs(templates): add template documentation"
git push
```

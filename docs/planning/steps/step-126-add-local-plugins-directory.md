# Step 126 — Add local plugins directory

**Phase:** `07-moro-cli`

## Purpose

Create a local plugin home for project-specific `moro` extensions.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p tools/moro-plugins

cat > tools/moro-plugins/README.md <<'EOF'
# Local moro Plugins

This directory is reserved for repository-local `moro` plugins.

Local plugins may add project-specific commands, generators, validators, profiles, or templates.
EOF
```

## Validate

```bash
test -f tools/moro-plugins/README.md
```

## Commit

```bash
git add .
git commit -m "chore(cli): add local plugin directory"
git push
```

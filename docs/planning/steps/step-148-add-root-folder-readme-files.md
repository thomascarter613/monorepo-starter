# Step 148 — Add root folder README files

**Phase:** `09-workspace-skeleton`

## Purpose

Replace placeholder `.gitkeep`-only folders with explanatory README files.

## Commands

Run from the repository root unless stated otherwise.

```bash
for dir in apps services packages libs tools configs contracts infra policies tests examples templates profiles scripts; do
  if [ ! -f "$dir/README.md" ]; then
    cat > "$dir/README.md" <<EOF
# $dir

This directory is part of the canonical `monorepo-starter` root structure.
EOF
  fi
done
```

## Validate

```bash
test -f apps/README.md && test -f services/README.md
```

## Commit

```bash
git add .
git commit -m "docs(repo): add root folder readmes"
git push
```

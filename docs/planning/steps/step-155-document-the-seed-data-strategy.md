# Step 155 — Document the seed data strategy

**Phase:** `10-local-services-observability`

## Purpose

Add seed data documentation before creating demo fixtures.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p docs/development/data

cat > docs/development/data/seed-data.md <<'EOF'
# Seed Data Strategy

Seed data should make the generated project feel realistic without containing real personal or customer data.

## Seed Categories

- users
- organizations
- workspaces
- teams
- roles and permissions
- projects
- comments
- files
- billing plans
- events
- notifications
- feature flags
- audit logs
- analytics events
EOF
```

## Validate

```bash
test -f docs/development/data/seed-data.md
```

## Commit

```bash
git add .
git commit -m "docs(data): add seed data strategy"
git push
```

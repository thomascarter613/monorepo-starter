# Step 156 — Create the seed data folder

**Phase:** `10-local-services-observability`

## Purpose

Create the first seed data structure.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p data/seeds

cat > data/seeds/README.md <<'EOF'
# Seed Data

This directory contains safe, realistic seed data for local development and demos.
EOF

cat > data/seeds/projects.json <<'EOF'
[
  {
    "name": "Example Project",
    "slug": "example-project",
    "status": "active",
    "priority": "medium"
  }
]
EOF
```

## Validate

```bash
test -f data/seeds/projects.json
```

## Commit

```bash
git add .
git commit -m "chore(data): add seed data folder"
git push
```

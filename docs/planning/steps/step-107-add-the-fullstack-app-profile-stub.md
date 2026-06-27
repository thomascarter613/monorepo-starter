# Step 107 — Add the fullstack-app profile stub

**Phase:** `06-architecture-governance`

## Purpose

Create the first supported generated project profile.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p profiles/fullstack-app

cat > profiles/fullstack-app/profile.json <<'EOF'
{
  "name": "fullstack-app",
  "version": "0.0.0",
  "description": "Full-stack TypeScript application profile with web, API, packages, database, tests, docs, and local services.",
  "packageManager": "bun",
  "features": {
    "web": true,
    "api": true,
    "database": true,
    "auth": true,
    "jobs": true,
    "files": true,
    "search": true,
    "billing": true
  }
}
EOF

cat > profiles/fullstack-app/README.md <<'EOF'
# fullstack-app Profile

The `fullstack-app` profile is the first default generated project profile.
EOF
```

## Validate

```bash
test -f profiles/fullstack-app/profile.json
```

## Commit

```bash
git add .
git commit -m "feat(profiles): add fullstack app profile stub"
git push
```

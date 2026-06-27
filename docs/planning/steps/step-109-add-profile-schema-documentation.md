# Step 109 — Add profile schema documentation

**Phase:** `06-architecture-governance`

## Purpose

Document expected profile metadata fields before validation is implemented.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > profiles/README.md <<'EOF'
# Profiles

Profiles describe generated project shapes.

## Required Fields

- `name`
- `version`
- `description`
- `packageManager`
- `features`

## Initial Profile

- `fullstack-app`

## Future Profiles

- web app
- API service
- package
- CLI
- worker
- docs site
- AI agent
- mobile app
- desktop app
- browser extension
EOF
```

## Validate

```bash
test -f profiles/README.md
```

## Commit

```bash
git add .
git commit -m "docs(profiles): add profile schema notes"
git push
```

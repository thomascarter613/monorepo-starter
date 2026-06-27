# Step 034 — Add the maintenance policy

**Phase:** `01-github-governance`

## Purpose

Define how dependencies, security fixes, deprecations, support windows, and maintenance work are handled.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/governance/maintenance-policy.md <<'EOF'
# Maintenance Policy

This policy defines how `monorepo-starter` should be maintained over time.

## Dependency Updates

Dependencies should be updated through documented automation where practical. Updates that affect runtime behavior, generated code, security posture, or developer workflow require review.

## Security Updates

Security patches should be prioritized ahead of normal feature work when risk is material.

## Deprecations

Deprecated commands, profiles, templates, or packages should have:

- a documented replacement
- a migration note
- a removal target when possible

## Support Windows

Formal support windows will be defined before a stable public release.

## Maintenance Rule

Maintenance work should preserve the golden path, avoid unnecessary churn, and keep the starter usable by a solo developer.
EOF
```

## Validate

```bash
test -f docs/governance/maintenance-policy.md
```

## Commit

```bash
git add .
git commit -m "docs(governance): add maintenance policy"
git push
```

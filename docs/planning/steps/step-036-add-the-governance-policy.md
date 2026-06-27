# Step 036 — Add the governance policy

**Phase:** `01-github-governance`

## Purpose

Create the project governance baseline for decisions, changes, reviews, and future contributors.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/governance/governance-policy.md <<'EOF'
# Governance Policy

This project uses lightweight but explicit governance.

## Decision Governance

Significant technical, architectural, tooling, workflow, or governance decisions must be recorded as ADRs.

## Change Governance

Changes should be small, reviewable, documented, and validated.

## Maintainer Model

The project currently has a single maintainer. Future maintainers may be added with clear ownership areas and CODEOWNERS entries.

## Review Model

Before branch protection is enabled, the maintainer may commit directly. After CI and branch protection are enabled, pull requests should be the default workflow.

## AI Governance

AI-generated changes are allowed, but humans remain accountable for correctness, safety, licensing, and maintainability.
EOF
```

## Validate

```bash
test -f docs/governance/governance-policy.md
```

## Commit

```bash
git add .
git commit -m "docs(governance): add governance policy"
git push
```

# Step 038 — Add the governance document index

**Phase:** `01-github-governance`

## Purpose

Create a single index for governance docs so contributors can find them quickly.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/governance/README.md <<'EOF'
# Governance

This directory contains governance, policy, risk, and repository-management documents.

## Documents

- [GitHub Label Taxonomy](./github-labels.md)
- [Governance Policy](./governance-policy.md)
- [Maintenance Policy](./maintenance-policy.md)
- [Support Policy](./support-policy.md)
- [Risk Register](./risks/risk-register.md)

## Rule

Governance documents should be updated when repository rules, ownership, reviews, policies, quality gates, or release expectations change.
EOF
```

## Validate

```bash
test -f docs/governance/README.md
```

## Commit

```bash
git add .
git commit -m "docs(governance): add governance index"
git push
```

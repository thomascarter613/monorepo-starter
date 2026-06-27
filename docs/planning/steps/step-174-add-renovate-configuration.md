# Step 174 — Add Renovate configuration

**Phase:** `12-release-ci`

## Purpose

Add dependency update automation configuration.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > renovate.json <<'EOF'
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["config:recommended"],
  "labels": ["type: task", "area: tooling", "automation: generated"],
  "rangeStrategy": "pin",
  "packageRules": [
    {
      "matchUpdateTypes": ["major"],
      "addLabels": ["risk: breaking-change"]
    }
  ]
}
EOF

cat > docs/governance/dependency-updates.md <<'EOF'
# Dependency Updates

Renovate is the default dependency update automation tool.

Major updates require extra review.
EOF
```

## Validate

```bash
test -f renovate.json
```

## Commit

```bash
git add .
git commit -m "chore(deps): add renovate configuration"
git push
```

# Step 161 — Add Gitleaks configuration

**Phase:** `11-security-supply-chain`

## Purpose

Add the first secret scanning config.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > .gitleaks.toml <<'EOF'
title = "monorepo-starter gitleaks config"

[allowlist]
description = "Allow documented local placeholders"
paths = ["\\.env\\.example$"]
EOF

bun pm pkg set scripts.security:secrets="gitleaks detect --source . --config .gitleaks.toml --redact"
```

## Validate

```bash
test -f .gitleaks.toml
```

## Commit

```bash
git add .
git commit -m "chore(security): add gitleaks config"
git push
```

## Notes

Install gitleaks locally before running `bun run security:secrets`.

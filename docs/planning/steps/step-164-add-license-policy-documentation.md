# Step 164 — Add license policy documentation

**Phase:** `11-security-supply-chain`

## Purpose

Document the initial allowed and review-required license policy.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/governance/license-policy.md <<'EOF'
# License Policy

## Allowed by Default

- MIT
- Apache-2.0
- BSD-2-Clause
- BSD-3-Clause
- ISC

## Requires Review

- LGPL
- MPL
- EPL
- custom licenses

## Blocked by Default

- AGPL
- GPL for runtime dependencies
- unknown or missing licenses

## Rule

License exceptions must be documented before merge.
EOF
```

## Validate

```bash
test -f docs/governance/license-policy.md
```

## Commit

```bash
git add .
git commit -m "docs(governance): add license policy"
git push
```

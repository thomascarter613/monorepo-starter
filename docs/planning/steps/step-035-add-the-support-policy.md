# Step 035 — Add the support policy

**Phase:** `01-github-governance`

## Purpose

Define expected support behavior before the project becomes public-facing.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/governance/support-policy.md <<'EOF'
# Support Policy

`monorepo-starter` is currently private-first and pre-stable.

## Current Support Status

No formal support guarantees exist before v1.0.

## Future Support Channels

Future public support may include:

- GitHub issues
- GitHub discussions
- security advisories
- documentation updates
- release notes

## Response Expectations

Response expectations will be documented before public release.

## Scope

Support covers the starter repository, documented commands, generated profiles, and official templates. Community plugins and user-modified generated projects may have separate support rules later.
EOF
```

## Validate

```bash
test -f docs/governance/support-policy.md
```

## Commit

```bash
git add .
git commit -m "docs(governance): add support policy"
git push
```

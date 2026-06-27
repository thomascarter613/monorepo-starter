# Step 032 — Create the initial risk register

**Phase:** `01-github-governance`

## Purpose

Add formal risk tracking before the project accumulates many tools and automation paths.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p docs/governance/risks

cat > docs/governance/risks/risk-register.md <<'EOF'
# Risk Register

This register tracks project risks for `monorepo-starter`.

| ID | Risk | Probability | Impact | Mitigation | Status |
| --- | --- | --- | --- | --- | --- |
| R-001 | Scope grows faster than implementation capacity | High | High | Use milestones, profiles, and strict phase boundaries | Open |
| R-002 | Tooling complexity overwhelms beginner accessibility | Medium | High | Keep a golden path and document optional complexity | Open |
| R-003 | Multiple package-manager profiles create lockfile drift | Medium | High | Bun-first default; profile-specific lockfile validation | Open |
| R-004 | AI-generated changes bypass governance expectations | Medium | High | AGENTS.md, protected files, ADR rules, PR checklist | Open |
| R-005 | Security tooling creates false confidence before real review | Medium | Medium | Treat tools as gates, not proof of safety | Open |
| R-006 | CLI generators overwrite user work | Medium | High | Generated-file manifest, hashes, dry-run, conflict detection | Open |
| R-007 | v1 includes too many profiles before the foundation is stable | High | Medium | Build foundation first, then profile families | Open |
EOF
```

## Validate

```bash
test -f docs/governance/risks/risk-register.md
```

## Commit

```bash
git add .
git commit -m "docs(governance): add initial risk register"
git push
```

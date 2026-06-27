# Step 163 — Add OSV scanner script

**Phase:** `11-security-supply-chain`

## Purpose

Add the package vulnerability scanning script.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun pm pkg set scripts.security:osv="osv-scanner --lockfile bun.lock"

cat > docs/governance/security-scanning.md <<'EOF'
# Security Scanning

## Secret Scanning

```bash
bun run security:secrets
```

## Vulnerability Scanning

```bash
bun run security:trivy
bun run security:osv
```
EOF
```

## Validate

```bash
test -f docs/governance/security-scanning.md
```

## Commit

```bash
git add .
git commit -m "docs(security): add security scanning scripts and docs"
git push
```

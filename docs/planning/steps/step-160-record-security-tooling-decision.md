# Step 160 — Record security tooling decision

**Phase:** `11-security-supply-chain`

## Purpose

Record the security tooling baseline before adding configs.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0037-use-gitleaks-trivy-osv-and-sbom-tooling.md <<'EOF'
# ADR-0037: Use Gitleaks, Trivy, OSV, and SBOM Tooling

## Status

Accepted

## Date

2026-06-26

## Context

The starter needs security and supply-chain checks.

## Decision

Use Gitleaks for secret scanning, Trivy/OSV for vulnerability scanning, license policy checks, and CycloneDX SBOM generation.

## Consequences

Security posture becomes visible and automatable.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0037 | Use Gitleaks, Trivy, OSV, and SBOM Tooling | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0037" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): define security tooling baseline"
git push
```

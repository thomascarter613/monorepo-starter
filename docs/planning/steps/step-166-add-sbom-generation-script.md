# Step 166 — Add SBOM generation script

**Phase:** `11-security-supply-chain`

## Purpose

Add a CycloneDX SBOM generation script.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d @cyclonedx/cyclonedx-npm
mkdir -p reports/sbom
bun pm pkg set scripts.security:sbom="cyclonedx-npm --output-file reports/sbom/bom.json"
```

## Validate

```bash
bun run security:sbom || true
```

## Commit

```bash
git add .
git commit -m "chore(security): add sbom generation script"
git push
```

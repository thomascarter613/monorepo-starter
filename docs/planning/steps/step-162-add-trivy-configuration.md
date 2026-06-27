# Step 162 — Add Trivy configuration

**Phase:** `11-security-supply-chain`

## Purpose

Add a basic Trivy config for vulnerability and IaC scanning.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > trivy.yaml <<'EOF'
scan:
  skip-dirs:
    - node_modules
    - .git
    - coverage
    - dist
    - build
vulnerability:
  ignore-unfixed: true
EOF

bun pm pkg set scripts.security:trivy="trivy fs --config trivy.yaml ."
```

## Validate

```bash
test -f trivy.yaml
```

## Commit

```bash
git add .
git commit -m "chore(security): add trivy config"
git push
```

## Notes

Install trivy locally before running `bun run security:trivy`.

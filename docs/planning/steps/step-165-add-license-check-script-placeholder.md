# Step 165 — Add license check script placeholder

**Phase:** `11-security-supply-chain`

## Purpose

Create a placeholder script for license policy checks.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d license-checker-rseidelsohn
bun pm pkg set scripts.security:licenses="license-checker-rseidelsohn --summary"
```

## Validate

```bash
bun run security:licenses || true
```

## Commit

```bash
git add .
git commit -m "chore(security): add license check script"
git push
```

# Step 033 — Add the ADR index

**Phase:** `01-github-governance`

## Purpose

Create an index of architecture decisions so decision history is easier to navigate.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/index.md <<'EOF'
# ADR Index

This file indexes Architecture Decision Records for `monorepo-starter`.

| ADR | Title | Status |
| --- | --- | --- |
| ADR-0001 | Record Architecture Decisions | Accepted |
| ADR-0002 | Use Bun as the Default Runtime and Package Manager | Accepted |
| ADR-0003 | Use a Governance-Grade Root Folder Structure | Accepted |
| ADR-0004 | Use TypeScript as the Primary Language Layer | Accepted |
| ADR-0005 | Use Biome for Formatting and Linting | Accepted |
| ADR-0006 | Use moon for Monorepo Task Orchestration | Accepted |

## Maintenance Rule

Add every new ADR to this index in the same commit that creates the ADR.
EOF
```

## Validate

```bash
grep "ADR-0006" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): add decision index"
git push
```

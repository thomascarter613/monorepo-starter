# Step 040 — Add folder-structure documentation

**Phase:** `02-documentation-foundation`

## Purpose

Explain the purpose of each root directory in one dedicated architecture document.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/folder-structure.md <<'EOF'
# Folder Structure

This document explains the root folder structure.

| Folder | Purpose |
| --- | --- |
| `apps/` | User-facing applications |
| `services/` | Backend services and workers |
| `packages/` | Shared packages and the `moro` CLI |
| `libs/` | Internal libraries and domain modules |
| `tools/` | Developer tools and generators |
| `configs/` | Shared configuration |
| `contracts/` | API, event, schema, and protocol contracts |
| `infra/` | Docker, deployment, IaC, and environments |
| `policies/` | Governance and policy rules |
| `docs/` | Project documentation |
| `tests/` | Cross-project tests and fixtures |
| `examples/` | Example generated projects and usage patterns |
| `templates/` | Generator templates used by `moro` |
| `profiles/` | Project/app/service/package generation profiles |
| `scripts/` | Root automation scripts |
| `.github/` | GitHub workflows, templates, and repo automation |
| `.devcontainer/` | Development container setup |
| `.moro/` | Starter metadata, generated manifests, and evolution state |
EOF
```

## Validate

```bash
test -f docs/architecture/folder-structure.md
```

## Commit

```bash
git add .
git commit -m "docs(architecture): document folder structure"
git push
```

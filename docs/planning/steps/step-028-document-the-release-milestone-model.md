# Step 028 — Document the release milestone model

**Phase:** `01-github-governance`

## Purpose

Define the initial milestone model before creating GitHub milestones.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p docs/roadmap

cat > docs/roadmap/milestones.md <<'EOF'
# Milestones

This document defines the default release milestone model for `monorepo-starter`.

## v0.1 Bootstrap Foundation

Establish the repository foundation, governance documents, ADRs, package-manager baseline, TypeScript baseline, formatting, linting, moon task orchestration, and GitHub templates.

## v0.2 Tooling Foundation

Add the core developer tooling baseline: commit checks, git hooks, markdown/YAML/shell validation, dependency consistency, dead-code detection, unit tests, e2e test baseline, and architecture checks.

## v0.3 Security and Supply Chain

Add secret scanning, vulnerability scanning, license policy, SBOM generation, provenance planning, release signing preparation, and security documentation.

## v0.4 `moro` CLI Foundation

Add the initial `moro` CLI package, command skeletons, config loading, doctor/check/plan/init commands, generated-file metadata, and template/profile foundations.

## v0.5 Workspace Skeleton

Add placeholder applications, services, packages, local infrastructure, seed data structure, API contracts, and package boundaries.

## v1.0 Governance-Ready Starter

Complete a usable, documented, CI-validated, policy-aware starter foundation that can be used as the base for real applications and future profile expansion.
EOF
```

## Validate

```bash
test -f docs/roadmap/milestones.md
```

## Commit

```bash
git add .
git commit -m "docs(roadmap): define release milestones"
git push
```

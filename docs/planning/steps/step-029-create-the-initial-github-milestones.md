# Step 029 — Create the initial GitHub milestones

**Phase:** `01-github-governance`

## Purpose

Create repository milestones corresponding to the documented release model.

## Commands

Run from the repository root unless stated otherwise.

```bash
gh milestone create "v0.1 Bootstrap Foundation" --description "Repository foundation, governance, ADRs, Bun, TypeScript, Biome, moon, and GitHub templates." || true
gh milestone create "v0.2 Tooling Foundation" --description "Core developer tooling, hooks, linting, dependency checks, tests, and architecture checks." || true
gh milestone create "v0.3 Security and Supply Chain" --description "Secret scanning, vulnerability scanning, license policy, SBOM, provenance, and security docs." || true
gh milestone create "v0.4 moro CLI Foundation" --description "Initial moro CLI, command skeletons, config loading, doctor/check/plan/init, metadata, templates, and profiles." || true
gh milestone create "v0.5 Workspace Skeleton" --description "Placeholder apps, services, packages, local infra, seed data, API contracts, and boundaries." || true
gh milestone create "v1.0 Governance-Ready Starter" --description "Usable, documented, CI-validated, policy-aware starter foundation." || true

gh milestone list
```

## Validate

```bash
gh milestone list | grep "v1.0 Governance-Ready Starter"
```

## Commit

```bash
git add .
git commit -m "chore(github): create initial milestones"
git push
```

## Notes

This step changes GitHub repository metadata. It may not create a commit unless you adjust local docs.

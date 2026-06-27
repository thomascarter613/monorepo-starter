# Step 030 — Add the v1 roadmap overview

**Phase:** `01-github-governance`

## Purpose

Create a human-readable roadmap that connects milestones to the charter and future work.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/roadmap/roadmap.md <<'EOF'
# Roadmap

This roadmap translates the project charter into a staged implementation path.

## v0.1 Bootstrap Foundation

- repository identity
- root structure
- ADR system
- Bun baseline
- TypeScript baseline
- Biome baseline
- moon baseline
- GitHub templates
- initial governance docs

## v0.2 Tooling Foundation

- git hooks
- commit validation
- markdown linting
- YAML linting
- shell linting
- dependency consistency
- dead-code detection
- unit test baseline
- e2e test baseline
- architecture boundary checks

## v0.3 Security and Supply Chain

- secret scanning
- vulnerability scanning
- license policy
- SBOM generation
- release provenance plan
- artifact signing plan
- security CI checks

## v0.4 moro CLI Foundation

- CLI package
- command skeletons
- config loader
- doctor/check/plan/init commands
- generated-file manifest
- profile model
- template model
- plugin interfaces

## v0.5 Workspace Skeleton

- apps skeleton
- services skeleton
- packages skeleton
- local infrastructure
- OpenAPI contract skeleton
- seed data skeleton
- observability skeleton

## v1.0 Governance-Ready Starter

- stable validation command
- documented setup
- CI quality gates
- security checks
- release readiness
- starter usage documentation
- known limitations documented
EOF
```

## Validate

```bash
test -f docs/roadmap/roadmap.md
```

## Commit

```bash
git add .
git commit -m "docs(roadmap): add v1 roadmap overview"
git push
```

0009-add-root-README.md

## Step 9 — Add the root `README.md`

Now create the repository’s front door. The charter is the deep source-of-truth document, but the root `README.md` should be the first thing a human, GitHub viewer, future contributor, or AI agent reads. Your charter defines the project as private-first but open-source ready, so this should exist early. 

From the repo root, run:

````bash
cat > README.md <<'EOF'
# monorepo-starter

A governance-grade, supply-chain-aware, policy-driven monorepo starter for building modern applications, services, packages, CLIs, documentation systems, and full product platforms.

`monorepo-starter` is designed to become more than a static repository template. It is intended to evolve into a full monorepo operating system with a built-in CLI, profile-based scaffolding, repository health checks, lifecycle automation, generated-file tracking, project evolution support, and AI-ready workflows.

## Status

Draft / early foundation.

This repository currently contains the initial project charter, architecture decision records, root project manifest, Bun lockfile, and canonical folder structure.

## Project Goals

The project aims to provide:

- a reusable production-ready monorepo foundation
- strong default tooling and quality gates
- Bun-first TypeScript development
- clear repository structure
- governance and policy documentation
- CI/CD and release automation
- security and supply-chain checks
- profile-based project generation
- a built-in `moro` CLI
- local-first development
- Docker-first operations
- AI-agent-ready repository instructions

## Default Stack Direction

The default v1 direction is:

- Bun
- TypeScript
- mise
- moon
- Biome
- Lefthook
- Syncpack
- Knip
- Vitest
- Playwright
- Docker Compose
- GitHub Actions
- Renovate
- Changesets
- Gitleaks
- Trivy
- OpenSSF Scorecard
- Markdown/MDX documentation

## Repository Structure

```text
apps/          User-facing applications
services/      Backend services and workers
packages/      Shared packages, including the future moro CLI
libs/          Internal libraries and domain modules
tools/         Developer tools, scripts, and generators
configs/       Shared configuration
contracts/     API, event, schema, and protocol contracts
infra/         Docker, deployment, infrastructure, and environments
policies/      Governance, quality, security, and repository policies
docs/          Project, architecture, development, and lifecycle documentation
tests/         Cross-project tests, fixtures, and validation
examples/      Example generated projects and usage patterns
templates/     Generator templates used by moro
profiles/      Project, app, service, and package generation profiles
scripts/       Root automation scripts
.github/       GitHub workflows, issue templates, and PR templates
.devcontainer/ Development container setup
.moro/         Starter metadata, generated manifests, and evolution state
```

## Important Documents

* [`project-charter.md`](./project-charter.md)
* [`docs/architecture/decisions/`](./docs/architecture/decisions/)

## Current Development Rule

Before adding major tools, conventions, workflows, or architectural structure, record the decision as an ADR.

## License

MIT
EOF

````

Then commit:

```bash
git add README.md
git commit -m "docs(repo): add root readme"
git push
````

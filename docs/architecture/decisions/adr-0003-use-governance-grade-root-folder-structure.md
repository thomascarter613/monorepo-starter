# ADR-0003: Use a Governance-Grade Root Folder Structure

## Status

Accepted

## Date

2026-06-26

## Context

`monorepo-starter` is not intended to be a minimal application scaffold.

The project charter defines it as a reusable, production-ready, governance-grade, supply-chain-aware, policy-driven monorepo foundation with lifecycle automation, documentation, profiles, templates, generated-file tracking, repository evolution support, and a built-in CLI.

The repository needs clear top-level boundaries for applications, backend services, packages, internal libraries, tooling, shared configuration, contracts, infrastructure, policies, documentation, tests, examples, templates, profiles, scripts, GitHub automation, development containers, and `moro` metadata.

If these concerns are mixed together or introduced ad hoc later, the repository will become harder to understand, harder to automate, harder to govern, and harder for AI agents to navigate safely.

## Decision

The repository will use a full root folder structure from the beginning:

```text
apps/
services/
packages/
libs/
tools/
configs/
contracts/
infra/
policies/
docs/
tests/
examples/
templates/
profiles/
scripts/
.github/
.devcontainer/
.moro/
```

Each top-level folder represents a distinct architectural, operational, governance, documentation, or automation concern.

The default structure favors clarity, long-term maintainability, automation readiness, and future repository evolution over short-term minimalism.

## Consequences

The project starts with more folders than a minimal starter repository.

This makes the repository feel larger at first, but it avoids later restructuring and gives every major concern a stable home from the beginning.

Tooling, documentation, generators, policies, and AI-agent instructions can rely on predictable locations.

The `moro` CLI can eventually validate the repository structure through `moro doctor`.

Generated projects can choose smaller profiles later, but the starter itself will maintain the full governance-grade structure.

## Alternatives Considered

### Minimal structure with only `apps/` and `packages/`

Rejected. This would be simpler initially but would not match the full lifecycle, governance, automation, and evolution goals of the project.

### Add folders only when needed

Rejected. This encourages inconsistent growth and makes automation harder.

### Use one generic `src/` folder

Rejected. A generic source folder does not express the architectural differences between apps, services, packages, tools, policies, contracts, infrastructure, templates, and profiles.

### Separate repositories for tooling, docs, infrastructure, and examples

Rejected for v1. The project should remain self-contained so the starter, CLI, templates, policies, documentation, and examples evolve together.

## Follow-up Work

* Add README files explaining the purpose of each root folder.
* Add repository structure documentation under `docs/architecture/`.
* Add root-folder validation to the future `moro doctor`.
* Add CODEOWNERS coverage for the root folder structure.
* Add AI-agent guidance explaining which folders are safe to modify casually and which require extra care.

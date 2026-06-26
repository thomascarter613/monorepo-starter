# ADR-0006: Use moon for Monorepo Task Orchestration

## Status

Accepted

## Date

2026-06-26

## Context

`monorepo-starter` needs a default monorepo task runner.

The project will eventually include multiple apps, services, packages, libraries, tools, configs, contracts, tests, documentation, templates, profiles, and the `moro` CLI.

The repository needs a consistent way to define, run, cache, inspect, and compose tasks such as:

```text
format
lint
typecheck
test
build
check
dev
clean
doctor
security
release
```

The project charter defines moon as the default monorepo task runner, with Turborepo, Nx, and Lage listed as alternatives.

## Decision

`monorepo-starter` will use moon as the default monorepo task runner.

moon will be responsible for workspace-aware task orchestration across apps, services, packages, libraries, tools, and configs.

The repository will use moon to coordinate project-level and root-level tasks such as:

```bash
moon run :format
moon run :lint
moon run :typecheck
moon run :test
moon run :build
moon run :check
```

The root `package.json` scripts may remain as convenient Bun entry points, but moon will become the canonical monorepo task orchestrator.

## Consequences

This gives the repository a structured, workspace-aware task system.

It supports future task graphs, project graphs, dependency-aware execution, CI integration, and architecture visibility.

It aligns with the charter’s goal of making the repository inspectable, automatable, and governance-ready.

It does add another core tool to the repository, so moon configuration should remain clear, documented, and validated by the future `moro doctor`.

## Alternatives Considered

### Turborepo

Turborepo is mature, popular, and strong for JavaScript/TypeScript monorepos.

Rejected as the default because the charter selects moon as the preferred orchestration layer and because moon provides a broader project-graph-oriented model that fits the governance-grade direction.

Turborepo may still be supported later as an alternative profile.

### Nx

Nx is powerful and full-featured.

Rejected as the default because it introduces more framework and plugin complexity than needed for the initial golden path.

Nx may still be documented or supported later as an advanced alternative.

### Lage

Rejected. Lage is capable, but it is less aligned with the long-term control-plane and repository-introspection goals of this project.

### Bun scripts only

Rejected. Bun scripts are useful entry points, but they are not enough for full monorepo-aware task orchestration, project graphs, dependency-aware execution, and future architecture validation.

## Follow-up Work

* Install or bootstrap moon.
* Add `.moon/` configuration.
* Define root-level task conventions.
* Update root `package.json` scripts to call moon where appropriate.
* Add moon project detection for apps, services, packages, libs, tools, and configs.
* Document common moon commands.
* Add moon validation to the future `moro doctor`.

# Contributing to monorepo-starter

Thank you for contributing to `monorepo-starter`.

This project is currently private-first and early-stage, but it is being structured as if it may become open-source and contributor-facing later.

## Project Source of Truth

The primary intent document is:

```text
project-charter.md
```

Major technical, architectural, workflow, governance, and tooling decisions must be recorded as Architecture Decision Records under:

```text
docs/architecture/decisions/
```

## Development Philosophy

Contributions should follow these principles:

* prefer clear structure over cleverness
* prefer documented decisions over implicit decisions
* prefer safe automation over magical automation
* prefer local-first workflows
* prefer reproducible commands
* prefer small, reviewable changes
* prefer governance from the beginning
* avoid adding tools without explaining why

## Branching

The default branch is:

```text
main
```

During early bootstrap, direct commits to `main` are acceptable.

Once CI and branch protection are configured, normal development should use short-lived branches and pull requests.

Recommended branch naming:

```text
feat/<short-description>
fix/<short-description>
docs/<short-description>
chore/<short-description>
refactor/<short-description>
```

Examples:

```text
feat/add-moro-cli-skeleton
docs/add-architecture-overview
chore/configure-biome
```

## Commit Messages

Use Conventional Commits.

Examples:

```text
chore(repo): add root package manifest
docs(adr): choose bun as default package manager
feat(cli): add moro command skeleton
fix(config): correct workspace package paths
```

Common commit types:

* `feat`
* `fix`
* `docs`
* `chore`
* `refactor`
* `test`
* `build`
* `ci`
* `perf`
* `security`

## Before Adding a Major Tool

Before adding a major dependency, tool, framework, workflow, or repository convention:

1. Create or update an ADR.
2. Explain the decision.
3. List alternatives considered.
4. Describe consequences.
5. Add the smallest useful implementation.

## Local Setup

Install Bun according to the version pinned in:

```text
mise.toml
```

Then install dependencies:

```bash
bun install
```

## Current Bootstrap Commands

The root scripts currently exist as placeholders until the actual tools are added.

Eventually, the expected validation command will be:

```bash
bun run check
```

## Pull Request Expectations

A good pull request should include:

* a clear title
* a focused scope
* relevant documentation updates
* an ADR when the change introduces a major decision
* tests when behavior changes
* notes about any follow-up work

## Protected Areas

Be careful when changing:

```text
project-charter.md
docs/architecture/decisions/
.moro/
policies/
.github/
infra/
```

These areas affect project intent, governance, automation, repository evolution, or delivery behavior.

## AI-Assisted Contributions

AI tools may be used, but contributors remain responsible for the final result.

AI-generated changes should be reviewed carefully for:

* correctness
* security
* maintainability
* license safety
* consistency with the charter
* consistency with ADRs
* unnecessary complexity

Do not accept AI-generated code or documentation that you do not understand.

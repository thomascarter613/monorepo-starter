# ADR-0008: Use Conventional Commits

## Status

Accepted

## Date

2026-06-26

## Context

The repository needs consistent commit messages for history, changelogs, releases, automation, and contributor clarity.

## Decision

Use Conventional Commits for all commits.

Examples:

```text
feat(cli): add moro command skeleton
docs(adr): choose biome for formatting and linting
chore(repo): add root gitignore
``

## Consequences

This supports future Changesets, release notes, changelog automation, and better repository history.

## Alternatives Considered

Informal commit messages were rejected because they weaken automation and long-term maintainability.

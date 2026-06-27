# ADR-0009: Use Lefthook for Git Hooks

## Status

Accepted

## Date

2026-06-26

## Context

The repository needs fast, local Git hooks for commit validation and pre-push checks.

## Decision

Use Lefthook as the default Git hook manager.

## Consequences

Contributors get consistent local checks before changes reach CI.

## Alternatives Considered

- simple-git-hooks: lighter, but less full-featured.
- pre-commit: powerful, but adds a Python-oriented workflow.

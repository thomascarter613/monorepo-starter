# ADR-0007: Use Trunk-Based Development with GitHub Flow

## Status

Accepted

## Date

2026-06-26

## Context

The project needs a simple branch strategy that works for a solo maintainer now and contributors later.

## Decision

Use trunk-based development with `main` as the protected trunk and short-lived GitHub Flow-style pull request branches.

## Consequences

The workflow remains simple, reviewable, and CI-friendly.

## Alternatives Considered

- Git Flow: rejected as too heavy for this project.
- Long-lived environment branches: rejected for v1.

## Follow-up Work

- Document the branch strategy.
- Enable branch protection after CI exists.

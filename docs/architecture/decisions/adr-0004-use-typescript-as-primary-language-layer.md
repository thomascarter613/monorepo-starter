# ADR-0004: Use TypeScript as the Primary Language Layer

## Status

Accepted

## Date

2026-06-26

## Context

`monorepo-starter` needs a primary implementation language for applications, packages, services, tooling, generators, shared configuration, and the `moro` CLI.

The project charter defines the starter as Bun-first and TypeScript-first. It also states that the `moro` CLI will be written in TypeScript and run on Bun.

The project may eventually support other languages such as Go, Rust, Python, Java, or PHP through profiles, services, tools, or generated project types, but v1 needs one clear default language path.

## Decision

`monorepo-starter` will use TypeScript as the primary language layer for v1.

TypeScript will be the default language for:

```text
apps/
services/
packages/
libs/
tools/
configs/
scripts/
packages/moro/
```

Other languages may be supported later through explicit profiles, adapters, or specialized services, but they will not replace TypeScript as the default v1 implementation language.

## Consequences

This gives the project a consistent language foundation across applications, services, shared packages, configuration, generators, and CLI tooling.

It aligns with the Bun-first runtime strategy.

It allows shared types, validation schemas, API contracts, generated clients, and developer tooling to work coherently across the monorepo.

It keeps the first implementation path focused instead of splitting the early repository across too many languages.

Supporting additional languages later will require clear boundaries, separate toolchains, separate quality gates, and profile-specific documentation.

## Alternatives Considered

### JavaScript as the primary language

Rejected. JavaScript is simpler, but TypeScript provides stronger safety, better editor support, better refactoring support, and clearer contracts for a governance-grade starter.

### Go as the primary language

Rejected for v1. Go is excellent for CLIs and backend services, but it does not align as directly with the Bun-first, TypeScript-first default stack.

### Rust as the primary language

Rejected for v1. Rust is strong for high-performance tooling, but it would increase early implementation complexity and make the starter less beginner-accessible.

### Polyglot-first from day one

Rejected. The project may become polyglot through profiles, but the default path should remain coherent and approachable.

## Follow-up Work

* Add the root TypeScript configuration.
* Add shared TypeScript config packages later under `packages/tsconfig` or `configs/`.
* Add TypeScript typecheck scripts.
* Add TypeScript support to the future `moro doctor`.
* Define package boundary rules for TypeScript imports.

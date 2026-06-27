# GitHub Label Taxonomy

This document defines the default GitHub label taxonomy for `monorepo-starter`.

Labels should make work easy to triage, filter, automate, and report on.

## Type Labels

```text
type: feature
type: bug
type: docs
type: task
type: adr
type: refactor
type: test
type: build
type: ci
type: security
type: governance
type: release
```

## Status Labels

```text
status: needs triage
status: needs decision
status: ready
status: blocked
status: in progress
status: needs review
status: done
```

## Priority Labels

```text
priority: critical
priority: high
priority: medium
priority: low
```

## Area Labels

```text
area: repo
area: docs
area: architecture
area: governance
area: tooling
area: ci
area: security
area: supply-chain
area: cli
area: templates
area: profiles
area: apps
area: services
area: packages
area: infra
area: testing
area: release
```

## Effort Labels

```text
effort: small
effort: medium
effort: large
effort: epic
```

## Risk Labels

```text
risk: low
risk: medium
risk: high
risk: breaking-change
```

## Automation Labels

```text
automation: candidate
automation: generated
automation: needs-sync
automation: do-not-automate
```

## Label Rules

Every issue should usually have:

* one `type:*` label
* one `status:*` label
* one or more `area:*` labels
* one `priority:*` label when priority is known
* one `effort:*` label when effort is known

Security-sensitive issues should use:

```text
type: security
```

Architecture-decision issues should use:

```text
type: adr
status: needs decision
```

Generated or automation-managed issues should be clearly labeled so humans understand which work may be synchronized by future `moro` automation.

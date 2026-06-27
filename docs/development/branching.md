# Branching Strategy

`monorepo-starter` uses trunk-based development with GitHub Flow-style pull requests.

## Branches

The default branch is:

```text
main
``

Work branches should be short-lived:

```text
feat/add-moro-cli-skeleton
docs/add-architecture-overview
chore/configure-biome
``

## Rule

Once CI and branch protection exist, changes should merge through pull requests with required checks.

0016-biome-for-formatting-and-linting.md

## Step 16 — Record the formatting and linting decision

Now create **ADR-0005: Use Biome for formatting and linting**.

Before installing Biome or creating `biome.json`, record the decision. Your charter names Biome as the default formatter/linter and treats formatting/linting as required v1 quality gates. 

From the repo root, run:

````bash
cat > docs/architecture/decisions/adr-0005-use-biome-for-formatting-and-linting.md <<'EOF'
# ADR-0005: Use Biome for Formatting and Linting

## Status

Accepted

## Date

2026-06-26

## Context

`monorepo-starter` needs a default formatting and linting strategy for TypeScript, JavaScript, JSON, and related project files.

The project charter defines Biome as the default formatting and linting tool. The repository is intended to be Bun-first, TypeScript-first, automation-friendly, and governance-grade.

Formatting and linting should be fast, consistent, easy to run locally, and suitable for CI quality gates.

## Decision

`monorepo-starter` will use Biome as the default formatter and linter.

Biome will be responsible for:

```text
formatting
linting
import organization where supported
basic code-quality enforcement
CI formatting checks
CI lint checks
```

The default root commands will be:

```bash
bun run format
bun run format:check
bun run lint
```

Biome configuration will live at the repository root in:

```text
biome.json
```

## Consequences

This gives the repository a fast, unified formatting and linting baseline.

It reduces the need for separate formatter and linter stacks during the initial implementation.

It aligns well with a Bun-first TypeScript repository.

Some ecosystem-specific lint rules may not be available in Biome. If the project later needs framework-specific or security-specific rules beyond Biome, additional tools may be introduced through separate ADRs.

## Alternatives Considered

### ESLint and Prettier

ESLint and Prettier are mature, widely adopted, and highly configurable.

Rejected as the default v1 baseline because they introduce more dependency and configuration surface area than needed for the initial starter foundation.

They may still be added later for specialized framework, accessibility, security, or custom rules if Biome alone is insufficient.

### Oxlint and Prettier

Rejected for now. Oxlint is promising and fast, but Biome provides a more complete default formatter/linter path for the first baseline.

### Prettier only

Rejected. Formatting alone is not enough for the repository’s quality-gate goals.

### No formatter/linter initially

Rejected. Formatting and linting are baseline quality gates and should exist early.

## Follow-up Work

* Install Biome.
* Add `biome.json`.
* Wire `format`, `format:check`, and `lint` scripts.
* Add Biome checks to the future CI workflow.
* Add Biome validation to the future `moro doctor`.
EOF

````

Then commit:

```bash
git add docs/architecture/decisions/adr-0005-use-biome-for-formatting-and-linting.md
git commit -m "docs(adr): choose biome for formatting and linting"
git push
````

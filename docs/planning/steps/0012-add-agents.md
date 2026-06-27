0012-add-agents.md

## Step 12 — Add root `AGENTS.md`

Now add the primary AI-agent operating guide. Your charter treats AI-readiness as a first-class repo capability, and specifically names `AGENTS.md` as the main instruction file for agents working in the repository. 

From the repo root, run:

````bash
cat > AGENTS.md <<'EOF'
# AGENTS.md

This file provides operating instructions for AI agents working in `monorepo-starter`.

`monorepo-starter` is a governance-grade, supply-chain-aware, policy-driven monorepo starter with lifecycle automation, profile-based scaffolding, repository evolution support, and a future built-in CLI named `moro`.

AI agents may assist with planning, documentation, implementation, testing, refactoring, review, and maintenance, but they must preserve the project charter, ADR history, repository structure, and governance rules.

## Primary Source of Truth

Read these files before making significant changes:

```text
project-charter.md
README.md
CONTRIBUTING.md
docs/architecture/decisions/
```

The project charter defines the product vision, scope, stack, structure, governance expectations, and long-term direction.

Architecture Decision Records explain why foundational decisions were made.

## Current Project Status

This repository is in early bootstrap.

Do not assume all tools are installed yet.

Root scripts may exist as placeholders until the corresponding tools are added.

## Operating Principles

Follow these principles:

* make small, reviewable changes
* prefer explicit structure over hidden magic
* prefer documented decisions over implicit decisions
* do not add major tools without an ADR
* do not silently change project direction
* preserve Bun-first behavior unless an ADR says otherwise
* preserve the canonical root folder structure
* avoid destructive commands unless explicitly requested
* explain non-obvious changes in commits or docs
* keep generated and handwritten files clearly distinguishable

## Before Making a Major Change

Before adding or changing any major tool, framework, dependency, workflow, policy, or architectural convention:

1. Check whether an ADR already exists.
2. If not, create a new ADR first.
3. Implement the smallest useful version of the change.
4. Update documentation if behavior, structure, or workflow changes.

Major changes include:

* package manager strategy
* monorepo task runner
* formatter or linter
* TypeScript configuration
* app framework
* API framework
* database layer
* authentication layer
* CI/CD workflows
* release automation
* security tooling
* governance policy
* folder structure
* `moro` CLI architecture

## Protected Files and Directories

Treat these as high-care areas:

```text
project-charter.md
docs/architecture/decisions/
.moro/
policies/
.github/
infra/
package.json
bun.lock
mise.toml
AGENTS.md
```

Do not rewrite these casually.

Changes to these areas should be deliberate, minimal, and documented.

## Commands

Prefer Bun commands.

Expected baseline commands will eventually include:

```bash
bun install
bun run check
bun run format
bun run lint
bun run typecheck
bun run test
bun run build
```

Do not assume a command works until the relevant tool has been installed and configured.

## Package Manager Rules

The default package manager is Bun.

The canonical default lockfile is:

```text
bun.lock
```

Do not add `pnpm-lock.yaml`, `package-lock.json`, or `yarn.lock` unless implementing a documented alternative package-manager profile.

## Documentation Rules

Update documentation when changing:

* project structure
* setup steps
* commands
* architecture
* development workflow
* governance rules
* quality gates
* security posture
* release process

Prefer Markdown that is clear, direct, and command-oriented.

## ADR Rules

Use ADRs for important decisions.

ADR files live in:

```text
docs/architecture/decisions/
```

Use numbered filenames:

```text
adr-0001-record-architecture-decisions.md
adr-0002-use-bun-as-default-runtime-and-package-manager.md
```

Do not renumber existing ADRs.

## Git and Commit Rules

Use Conventional Commits.

Examples:

```text
docs(adr): choose bun as default runtime and package manager
chore(repo): add root gitignore
feat(cli): add moro command skeleton
fix(config): correct workspace paths
```

Prefer focused commits.

Do not mix unrelated changes.

## Safety Rules

Do not:

* delete user work without explicit instruction
* replace large files unnecessarily
* introduce secrets
* commit `.env` files
* bypass documented quality gates
* weaken governance without an ADR
* add dependencies without a clear reason
* invent project requirements that conflict with the charter

## AI Review Expectations

Before presenting changes, check for:

* consistency with the charter
* consistency with ADRs
* correct file placement
* minimal scope
* clear naming
* missing docs
* obvious security issues
* broken commands
* unnecessary complexity

## Current Golden Rule

When in doubt, preserve the charter, create an ADR, make the smallest safe change, and document what changed.
EOF

````

Then commit:

```bash
git add AGENTS.md
git commit -m "docs(repo): add ai agent instructions"
git push
````

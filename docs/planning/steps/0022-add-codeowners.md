0022-add-codeowners.md

## Step 22 — Add `.github/CODEOWNERS`

Now add repository ownership rules. Even as a solo developer, this establishes the governance pattern early and makes the repo ready for future contributors, protected branches, and required reviews. Your charter explicitly includes `CODEOWNERS` as part of repo governance. 

From the repo root, run:

```bash
OWNER="$(gh api user -q .login)"

cat > .github/CODEOWNERS <<EOF
# CODEOWNERS for monorepo-starter
#
# This repository is currently maintained by a single owner.
# Ownership can be expanded later as contributors, package owners,
# service owners, security reviewers, and release maintainers are added.

# Default ownership
* @$OWNER

# Project intent and governance
/project-charter.md @$OWNER
/README.md @$OWNER
/CONTRIBUTING.md @$OWNER
/SECURITY.md @$OWNER
/AGENTS.md @$OWNER
/LICENSE @$OWNER

# Architecture decisions
/docs/architecture/decisions/ @$OWNER

# Repository automation and CI/CD
/.github/ @$OWNER

# Tooling and package management
/package.json @$OWNER
/bun.lock @$OWNER
/mise.toml @$OWNER
/tsconfig.json @$OWNER
/tsconfig.base.json @$OWNER
/biome.json @$OWNER
/moon.yml @$OWNER
/.moon/ @$OWNER

# Governance, policy, and security
/policies/ @$OWNER
/.moro/ @$OWNER

# Infrastructure and environments
/infra/ @$OWNER
/.devcontainer/ @$OWNER

# CLI, generators, templates, and profiles
/packages/moro/ @$OWNER
/tools/ @$OWNER
/templates/ @$OWNER
/profiles/ @$OWNER
/scripts/ @$OWNER
EOF
```

Verify:

```bash
cat .github/CODEOWNERS
```

Then commit:

```bash
git add .github/CODEOWNERS
git commit -m "chore(repo): add code owners"
git push
```

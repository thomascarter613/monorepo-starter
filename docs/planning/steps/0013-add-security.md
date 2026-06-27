0013-add-security.md

## Step 13 — Add `SECURITY.md`

Now add the repository’s security policy before adding security tooling. Your charter makes security, supply-chain checks, secret scanning, vulnerability scanning, provenance, and governance first-class parts of v1, so the repo should state how security issues are handled from the beginning. 

From the repo root, run:

````bash id="azpxxo"
cat > SECURITY.md <<'EOF'
# Security Policy

Security is a first-class concern for `monorepo-starter`.

This repository is intended to become a governance-grade, supply-chain-aware, policy-driven monorepo starter with security checks, secret scanning, dependency scanning, vulnerability scanning, license checks, SBOM generation, artifact signing, and release provenance.

## Supported Versions

The project is currently in early bootstrap and has not reached a stable release.

| Version | Supported |
| ------- | --------- |
| 0.x     | No stable security support yet |

Formal support windows will be defined before the first stable release.

## Reporting a Vulnerability

Do not publicly disclose suspected vulnerabilities until they have been reviewed.

For now, report security concerns privately to the repository owner.

A formal security contact, disclosure process, and GitHub Security Advisory workflow will be added before public release.

## Security Scope

Security-sensitive areas include:

```text
.github/
infra/
policies/
scripts/
packages/moro/
.moro/
package.json
bun.lock
mise.toml
AGENTS.md
```

Security-sensitive functionality includes:

* dependency management
* generated code
* repository automation
* GitHub Actions workflows
* release automation
* secret handling
* environment configuration
* authentication
* authorization
* file upload handling
* API boundaries
* plugin execution
* CLI commands that modify files
* generated-file tracking
* repository evolution logic

## Secret Handling

Never commit secrets.

Do not commit:

```text
.env
.env.*
*.pem
*.key
*.crt
*.p12
*.pfx
```

Allowed examples:

```text
.env.example
.env.local.example
.env.production.example
```

Example files must contain safe placeholder values only.

## Dependency and Supply-Chain Expectations

Before the first stable release, the project should include checks for:

* secret scanning
* vulnerability scanning
* dependency consistency
* license policy
* SBOM generation
* GitHub Actions hardening
* artifact signing
* build provenance
* release validation

The intended default tools will be introduced through ADRs before implementation.

## AI-Assisted Security Rule

AI agents may assist with security work, but they must not:

* introduce secrets
* weaken checks without an ADR
* disable security tooling casually
* bypass quality gates
* add unaudited dependencies without justification
* create unsafe code-generation behavior
* modify release or CI workflows without review

## Current Status

Security automation is not fully configured yet.

Until security tooling is installed, all security-relevant changes require extra manual review.
EOF

````

Then commit:

```bash id="m55te7"
git add SECURITY.md
git commit -m "docs(repo): add security policy"
git push
````

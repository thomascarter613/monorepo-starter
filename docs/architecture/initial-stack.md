## Initial Stack

| Function                     |                   Default   | Optional alternatives                              |
| ---------------------------- | --------------------------: | -------------------------------------------------- |
| Runtime / package manager    |                     **Bun** | pnpm, npm, Yarn                                    |
| Tool version manager         |                    **mise** | proto, asdf, Volta                                 |
| Monorepo task runner         |                    **moon** | Turborepo, Nx, Lage                                |
| JS/TS language layer         |              **TypeScript** | JavaScript, Go, Rust                               |
| Formatting / linting         |                   **Biome** | Oxlint, Rome-style toolchains                      |
| Git hooks                    |                **Lefthook** | simple-git-hooks, pre-commit                       |
| Dependency consistency       |                **Syncpack** | Manypkg, sherif, pnpm catalogs                     |
| Dead code / unused deps      |                    **Knip** | depcheck, ts-prune, unimported                     |
| Web app framework            |          **TanStack Start** | Next.js, Astro, SolidStart                         |
| UI framework                 |                 **SolidJS** | Reactjs, Vue, Svelte, Qwik                         |
| Styling                      |            **Tailwind CSS** | Panda CSS, UnoCSS, vanilla CSS modules             |
| Component system             | **shadcn-style components** | Ark UI, Radix UI, Headless UI                      |
| Icons                        |                  **Lucide** | Heroicons, Tabler Icons, Phosphor Icons            |
| API framework                |                  **Elysia** | Hono, Fastify, NestJS                              |
| API contract docs            |        **OpenAPI + Scalar** | Redocly, Swagger UI, OpenAPI Generator             |
| Type-safe API client         | **Eden / generated client** | tRPC, oRPC, OpenAPI clients                        |
| Runtime validation           |                 **ArkType** | Zod, Valibot, TypeBox                              |
| Database                     |              **PostgreSQL** | SQLite, MySQL/MariaDB, MongoDB                     |
| ORM / query layer            |                 **Drizzle** | Prisma, Kysely, TypeORM                            |
| DB migrations                |             **Drizzle Kit** | Atlas, Prisma Migrate, node-pg-migrate             |
| Auth                         |             **better-auth** | Auth.js, Supabase Auth, Ory Kratos                 |
| Cache / local queue backing  | **Redis-compatible Valkey** | Redis, Dragonfly, KeyDB                            |
| Job queue                    |                  **BullMQ** | pg-boss, Graphile Worker, Temporal                 |
| Object storage               |                   **MinIO** | S3, Cloudflare R2, Supabase Storage                |
| Unit tests                   |                  **Vitest** | Jest, Bun test, uvu                                |
| E2E tests                    |              **Playwright** | Cypress, WebdriverIO, TestCafe                     |
| Component docs/testing       |               **Storybook** | Ladle, Histoire, Styleguidist                      |
| Local services               |          **Docker Compose** | Podman Compose, Tilt, DevSpace                     |
| Dev environment              |           **Dev Container** | Nix, mise-only, Docker Compose only                |
| CI                           |          **GitHub Actions** | GitLab CI, CircleCI, Buildkite                     |
| Dependency updates           |                **Renovate** | Dependabot, npm-check-updates, Snyk                |
| Releases / changelogs        |              **Changesets** | semantic-release, release-it, Nx Release           |
| Secret scanning              |                **Gitleaks** | TruffleHog, GitHub secret scanning, detect-secrets |
| Vulnerability / IaC scanning |                   **Trivy** | Grype, Snyk, Checkov                               |
| OSS security score           |       **OpenSSF Scorecard** | Socket, osv-scanner, StepSecurity Harden-Runner    |
| Logging                      |                    **pino** | Winston, consola, loglevel                         |
| Observability                |           **OpenTelemetry** | Sentry, Axiom, HyperDX                             |
| Error tracking               |               **GlitchTip** | Sentry, Highlight.io, Bugsnag                      |
| Infrastructure as code       |                  **Pulumi** | Terraform/OpenTofu, SST, CDK                       |
| Deployment                   |            **Docker-first** | Vercel, Cloudflare Workers/Pages, Fly.io           |
| Docs                         |            **Markdown/MDX** | Astro Starlight, Docusaurus, VitePress             |
| Repo governance              |   **CODEOWNERS + policies** | OPA, Conftest, Danger JS                           |
| AI/agent instructions        |               **AGENTS.md** | CLAUDE.md, cursor rules, copilot instructions      |


`monorepo-starter` will use a:
- Bun-first, TypeScript-first monorepo stack,
- moon for task orchestration, 
- Biome for formatting and linting, 
- Lefthook for Git hooks, 
- Syncpack for dependency consistency, 
- Knip for dead-code detection, 
- Vitest for unit testing, 
- Playwright for end-to-end testing, 
- Docker Compose for local services, 
- GitHub Actions for CI, 
- Renovate for dependency updates, 
- Changesets for releases, 
- Gitleaks and Trivy for security scanning, and 
- Markdown/MDX documentation.

The default application profile will support full-stack TypeScript apps, APIs, packages, CLIs, workers, and documentation sites. 
Framework-specific profiles may include: 
- TanStack Start, 
- SolidStart, 
- Next.js, 
- Astro, 
- Elysia, 
- Hono, 
- Drizzle, 
- PostgreSQL, 
- Redis-compatible caching, 
- MinIO-compatible object storage, and 
- OpenAPI/Scalar documentation.


# Additionaal stack components

| Function                    |                           Default | Alternatives                                  |
| --------------------------- | --------------------------------: | --------------------------------------------- |
| Package-manager strategy    |      **Bun-first + pnpm profile** | Bun-only, pnpm-only                           |
| GitHub Actions linting      |                    **actionlint** | zizmor, GitHub workflow validation            |
| Commit standards            |                    **commitlint** | gitlint, custom Lefthook rules                |
| Markdown linting            |             **markdownlint-cli2** | remark-lint, Prettier                         |
| YAML linting                |                      **yamllint** | Spectral, prettier-plugin-yaml                |
| Shell lint/format           |            **ShellCheck + shfmt** | bashate, beautysh                             |
| License policy              |   **license-checker-rseidelsohn** | licensee, ScanCode                            |
| SBOM generation             |                     **CycloneDX** | SPDX, Syft                                    |
| Vulnerability DB scan       |                   **osv-scanner** | Trivy, Grype                                  |
| Artifact signing            |               **Sigstore Cosign** | GPG, minisign                                 |
| Build provenance            |               **SLSA provenance** | GitHub attestations, in-toto                  |
| Container hardening         |       **distroless/Wolfi images** | Alpine, Chainguard images                     |
| Policy-as-code              |                **OPA + Conftest** | Kyverno, js-policy tools                      |
| Architecture fitness checks |            **dependency-cruiser** | ArchUnitJS, custom moon checks                |
| Repo metadata validation    |            **custom repo doctor** | JSON Schema, CUE, Zod/ArkType                 |
| AI context governance       |             **AGENTS.md + rules** | CLAUDE.md, Cursor rules, Copilot instructions |
| Generated-code marking      |           **Linguist attributes** | custom `.gitattributes`, docs policy          |
| Release provenance          | **Changesets + signed artifacts** | semantic-release, release-it                  |
| Supply-chain score          |             **OpenSSF Scorecard** | Socket, StepSecurity Harden-Runner            |


The repository will be Bun-first by default, using `bun.lock` as the canonical default lockfile. 

A pnpm profile will be supported as an alternative generation mode, producing `pnpm-workspace.yaml`, `pnpm-lock.yaml`, and pnpm-specific dependency/catalog configuration when selected.

For v1, `monorepo-starter` will target a governance-grade, supply-chain-aware, policy-driven monorepo foundation. In addition to the core Bun-first TypeScript stack, it will include SBOM generation, artifact signing, build provenance, security scanning, license policy checks, workflow linting, architecture fitness checks, repository metadata validation, AI-agent instructions, and documented package-manager profiles for Bun-first usage with pnpm as a supported alternative.


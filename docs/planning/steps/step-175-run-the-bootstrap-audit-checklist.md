# Step 175 — Run the bootstrap audit checklist

**Phase:** `13-bootstrap-closeout`

## Purpose

Perform a closeout review for the bootstrap-to-governance-ready phase.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p reports/bootstrap

cat > reports/bootstrap/checklist.md <<'EOF'
# Bootstrap Audit Checklist

## Repository Foundation

- [ ] Charter committed
- [ ] README present
- [ ] LICENSE present
- [ ] CONTRIBUTING present
- [ ] SECURITY present
- [ ] AGENTS present
- [ ] ADRs indexed
- [ ] Root folder structure present

## Tooling

- [ ] Bun install works
- [ ] TypeScript works
- [ ] Biome works
- [ ] moon works
- [ ] commitlint works
- [ ] Lefthook works
- [ ] Vitest works
- [ ] Playwright installed
- [ ] Syncpack configured
- [ ] Knip configured
- [ ] dependency-cruiser configured

## Governance

- [ ] CODEOWNERS present
- [ ] PR template present
- [ ] Issue templates present
- [ ] Label taxonomy documented
- [ ] Milestones documented
- [ ] Risk register present
- [ ] Quality gates documented

## Security and Supply Chain

- [ ] Gitleaks config present
- [ ] Trivy config present
- [ ] License policy present
- [ ] SBOM script present
- [ ] Security workflow present

## Closeout Commands

```bash
bun install --frozen-lockfile
bun run format
bun run check
git status --short
```
EOF
```

## Validate

```bash
test -f reports/bootstrap/checklist.md
```

## Commit

```bash
git add .
git commit -m "docs(audit): add bootstrap audit checklist"
git push
```

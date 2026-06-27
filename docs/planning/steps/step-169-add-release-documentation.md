# Step 169 — Add release documentation

**Phase:** `12-release-ci`

## Purpose

Document the release process before release workflows exist.

## Commands

Run from the repository root unless stated otherwise.

```bash
mkdir -p docs/sdlc

cat > docs/sdlc/release.md <<'EOF'
# Release Process

## Add a Changeset

```bash
bun run changeset
```

## Version Packages

```bash
bun run version
```

## Publish

```bash
bun run release
```

## Rule

Public releases require passing CI, security checks, changelog review, and maintainer approval.
EOF
```

## Validate

```bash
test -f docs/sdlc/release.md
```

## Commit

```bash
git add .
git commit -m "docs(release): add release process"
git push
```

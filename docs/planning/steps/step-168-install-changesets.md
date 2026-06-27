# Step 168 — Install Changesets

**Phase:** `12-release-ci`

## Purpose

Add release note and version management tooling.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d @changesets/cli
bunx changeset init
bun pm pkg set scripts.changeset="changeset"
bun pm pkg set scripts.version="changeset version"
bun pm pkg set scripts.release="changeset publish"
```

## Validate

```bash
test -d .changeset
```

## Commit

```bash
git add .
git commit -m "chore(release): initialize changesets"
git push
```

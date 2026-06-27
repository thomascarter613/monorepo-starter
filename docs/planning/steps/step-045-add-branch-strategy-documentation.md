# Step 045 — Add branch strategy documentation

**Phase:** `02-documentation-foundation`

## Purpose

Document daily branch and pull request expectations.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/development/branching.md <<'EOF'
# Branching Strategy

`monorepo-starter` uses trunk-based development with GitHub Flow-style pull requests.

## Branches

The default branch is:

```text
main
```

Work branches should be short-lived:

```text
feat/add-moro-cli-skeleton
docs/add-architecture-overview
chore/configure-biome
```

## Rule

Once CI and branch protection exist, changes should merge through pull requests with required checks.
EOF
```

## Validate

```bash
test -f docs/development/branching.md
```

## Commit

```bash
git add .
git commit -m "docs(development): document branch strategy"
git push
```

# Step 027 — Create the GitHub labels

**Phase:** `01-github-governance`

## Purpose

Run the label sync script so repository labels match the documented taxonomy.

## Commands

Run from the repository root unless stated otherwise.

```bash
scripts/github/sync-labels.sh
gh label list --limit 100
```

## Validate

```bash
gh label list --limit 100 | grep "type: task"
```

## Commit

```bash
git add .
git commit -m "chore(github): sync repository labels"
git push
```

## Notes

This step changes GitHub repository metadata, not local files. Commit only if the script changed.

# Step 050 — Configure Lefthook hooks

**Phase:** `03-tooling-foundation`

## Purpose

Add commit-message and pre-push hooks that run the local quality baseline.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > lefthook.yml <<'EOF'
commit-msg:
  commands:
    commitlint:
      run: bunx commitlint --edit {1}

pre-push:
  commands:
    check:
      run: bun run check
EOF
```

## Validate

```bash
bunx lefthook run pre-push
```

## Commit

```bash
git add .
git commit -m "chore(git): configure lefthook hooks"
git push
```

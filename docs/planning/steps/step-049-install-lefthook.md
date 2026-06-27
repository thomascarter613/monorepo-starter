# Step 049 — Install Lefthook

**Phase:** `03-tooling-foundation`

## Purpose

Install Lefthook as the local Git hook manager.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun add -d lefthook
bun pm pkg set scripts.prepare="lefthook install"
bun run prepare
```

## Validate

```bash
bunx lefthook version
```

## Commit

```bash
git add .
git commit -m "chore(git): install lefthook"
git push
```

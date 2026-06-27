# Step 150 — Wire more checks into root validation

**Phase:** `09-workspace-skeleton`

## Purpose

Update the root check command so newer quality gates are included.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun pm pkg set scripts.check="moon run root:check && bun run deps:check && bun run deadcode && bun run arch && bun run lint:md"
```

## Validate

```bash
bun run check || true
```

## Commit

```bash
git add .
git commit -m "chore(repo): expand root validation command"
git push
```

## Notes

The command may need tuning as Knip and architecture checks become stricter.

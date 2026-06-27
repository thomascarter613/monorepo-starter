# Step 056 — Add shell validation scripts

**Phase:** `03-tooling-foundation`

## Purpose

Create Bun script entries for ShellCheck and shfmt.

## Commands

Run from the repository root unless stated otherwise.

```bash
bun pm pkg set scripts.lint:shell="find scripts -name '*.sh' -print0 | xargs -0 -r shellcheck"
bun pm pkg set scripts.format:shell="find scripts -name '*.sh' -print0 | xargs -0 -r shfmt -w"
bun pm pkg set scripts.format:shell:check="find scripts -name '*.sh' -print0 | xargs -0 -r shfmt -d"
```

## Validate

```bash
bun pm pkg get scripts.lint:shell
```

## Commit

```bash
git add .
git commit -m "chore(shell): add shell validation scripts"
git push
```

## Notes

Install shellcheck and shfmt through your OS package manager before running these scripts.

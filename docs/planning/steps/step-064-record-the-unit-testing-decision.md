# Step 064 — Record the unit testing decision

**Phase:** `03-tooling-foundation`

## Purpose

Record the decision to use Vitest before installing it.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0015-use-vitest-for-unit-tests.md <<'EOF'
# ADR-0015: Use Vitest for Unit Tests

## Status

Accepted

## Date

2026-06-26

## Context

The repository needs a default unit test runner for TypeScript packages and services.

## Decision

Use Vitest as the default unit test runner.

## Consequences

Packages get a fast, TypeScript-friendly test baseline.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0015 | Use Vitest for Unit Tests | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0015" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose vitest for unit tests"
git push
```

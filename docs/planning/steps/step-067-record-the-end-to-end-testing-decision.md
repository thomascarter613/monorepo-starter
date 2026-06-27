# Step 067 — Record the end-to-end testing decision

**Phase:** `03-tooling-foundation`

## Purpose

Record the decision to use Playwright before installing it.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0016-use-playwright-for-end-to-end-tests.md <<'EOF'
# ADR-0016: Use Playwright for End-to-End Tests

## Status

Accepted

## Date

2026-06-26

## Context

The starter will eventually include web apps, admin apps, docs apps, and generated profiles that need browser-level validation.

## Decision

Use Playwright for end-to-end and browser smoke tests.

## Consequences

The project has a production-grade browser testing path from v1.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0016 | Use Playwright for End-to-End Tests | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0016" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose playwright for e2e tests"
git push
```

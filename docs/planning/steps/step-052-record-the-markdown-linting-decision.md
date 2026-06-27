# Step 052 — Record the Markdown linting decision

**Phase:** `03-tooling-foundation`

## Purpose

Record the decision to use markdownlint-cli2 before installing it.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0010-use-markdownlint-for-markdown-quality.md <<'EOF'
# ADR-0010: Use markdownlint-cli2 for Markdown Quality

## Status

Accepted

## Date

2026-06-26

## Context

Documentation is a first-class artifact in this repository.

## Decision

Use markdownlint-cli2 for Markdown quality checks.

## Consequences

Documentation will have consistent structure and avoid common Markdown issues.
EOF

python - <<'PY'
from pathlib import Path
p = Path('docs/architecture/decisions/index.md')
text = p.read_text()
row = '| ADR-0010 | Use markdownlint-cli2 for Markdown Quality | Accepted |'
if row not in text:
    p.write_text(text.rstrip() + '\n' + row + '\n')
PY
```

## Validate

```bash
grep "ADR-0010" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose markdownlint for markdown quality"
git push
```

# Step 054 — Record YAML and shell validation decision

**Phase:** `03-tooling-foundation`

## Purpose

Record how YAML and shell scripts will be validated.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0011-use-yamllint-shellcheck-and-shfmt.md <<'EOF'
# ADR-0011: Use yamllint, ShellCheck, and shfmt

## Status

Accepted

## Date

2026-06-26

## Context

The repository will contain YAML workflows/configs and shell automation scripts.

## Decision

Use yamllint for YAML validation, ShellCheck for shell linting, and shfmt for shell formatting.

## Consequences

Shell and YAML automation will be safer and more consistent.
EOF

python - <<'PY'
from pathlib import Path
p = Path('docs/architecture/decisions/index.md')
text = p.read_text()
row = '| ADR-0011 | Use yamllint, ShellCheck, and shfmt | Accepted |'
if row not in text:
    p.write_text(text.rstrip() + '\n' + row + '\n')
PY
```

## Validate

```bash
grep "ADR-0011" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose yaml and shell validation tools"
git push
```

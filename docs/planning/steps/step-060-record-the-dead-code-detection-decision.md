# Step 060 — Record the dead-code detection decision

**Phase:** `03-tooling-foundation`

## Purpose

Record the decision to use Knip before adding it.

## Commands

Run from the repository root unless stated otherwise.

```bash
cat > docs/architecture/decisions/adr-0013-use-knip-for-unused-code-and-dependency-detection.md <<'EOF'
# ADR-0013: Use Knip for Unused Code and Dependency Detection

## Status

Accepted

## Date

2026-06-26

## Context

A starter repository can accumulate unused files, exports, and dependencies quickly.

## Decision

Use Knip for unused dependency, file, and export detection.

## Consequences

The repository has a tool for controlling dead code and dependency bloat.
EOF

python - <<'PY'
from pathlib import Path
p=Path('docs/architecture/decisions/index.md')
text=p.read_text()
row='| ADR-0013 | Use Knip for Unused Code and Dependency Detection | Accepted |'
if row not in text: p.write_text(text.rstrip()+'\n'+row+'\n')
PY
```

## Validate

```bash
grep "ADR-0013" docs/architecture/decisions/index.md
```

## Commit

```bash
git add .
git commit -m "docs(adr): choose knip for dead-code detection"
git push
```
